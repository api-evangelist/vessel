---
name: vessel-write-to-a-customers-crm
description: >-
  Create and update records in an end customer's CRM through Vessel's unified v2 API, safely — the
  API has no idempotency mechanism and returns some validation failures as 5xx, so naive retry logic
  duplicates records in a customer's system of record.
api: vessel:crm-unified-api
spec: openapi/vessel-crm-openapi.yml
operations:
  - get-info
  - create-contact
  - update-contact
  - create-deal
  - update-deal
  - create-account
  - update-account
  - create-lead
  - update-lead
  - create-note
  - create-task
  - get-details-crm-contact
generated: '2026-08-13'
method: generated
source: openapi/vessel-crm-openapi.yml + https://github.com/vesselapi/all-api-docs/blob/main/docs/pages/crm/error-handling.mdx
---

# Write to a customer's CRM

Writes here land in a customer's system of record. Two published properties of this API make that
riskier than it looks, and both are invisible in the OpenAPI.

## Read this before you write

1. **There is no idempotency mechanism.** No `Idempotency-Key` header, no client-supplied request id,
   no de-duplication. Grepped across all 20 published Vessel specs and the whole documentation
   repository on 2026-08-13: zero occurrences of "idempoten". A `create-contact` retried after a
   timeout creates a second contact in the customer's Salesforce.

2. **Some client errors arrive as 5xx.** Vessel documents this explicitly: "due to historical reasons,
   some user validation issues will be returned as 5xx", including referencing an object that does not
   exist and calling an endpoint the connected CRM does not implement. The usual rule — retry 5xx,
   don't retry 4xx — is wrong here and, combined with (1), turns one bad write into many.

**Therefore:** never auto-retry a write. On any failure, including a timeout, treat the outcome as
UNKNOWN and reconcile by reading before you write again.

## Steps

1. **Confirm the operation exists for this connection.**
   `POST /api/unifications/crm/info/find` (`get-info`). Not every downstream CRM implements every
   object.

2. **Reconcile first.** For a create, search for the record before creating it — e.g.
   `list-contacts` filtered by `email` (the one contact filter that does not require synced-cache).
   This is your idempotency, because the API does not provide one.

3. **Create.** `POST /api/unifications/crm/contacts/create` (`create-contact`) with `accessToken` and
   a `ContactCreate` body. Peers: `create-deal`, `create-account`, `create-lead`, `create-note`,
   `create-task`, `create-event`, `create-email`, `create-call`, `create-event-attendee`.

4. **Update.** `POST /api/unifications/crm/contacts/update` (`update-contact`) with the record id and
   a `ContactUpdate` body. Updates are the safer operation — they are naturally idempotent in effect
   even though the API guarantees nothing.

5. **Set relationships through `associations`**, not by embedding objects: `accountIds`, `dealIds`,
   `leadIds`, `ownerUserId`. See `data-model/vessel-data-model.yml`.

6. **Verify.** Read the record back with `get-contact`. When synced-cache is enabled Vessel updates
   the cache on writes made through its own API, so the read should be consistent immediately;
   changes made in the downstream UI can lag by up to an hour.

## Handling the error envelope

```json
{
  "message": "Invalid email address",
  "errorCode": "INVALID_FIELD_VALUE",
  "metadata": {
    "originalStatusCode": 400,
    "originalErrors": [
      { "message": "Email: invalid email address: 123123123",
        "errorCode": "INVALID_EMAIL_ADDRESS", "fields": ["Email"] }
    ]
  }
}
```

- `errorCode` is documented as **optional** — do not build control flow that requires it.
- When `metadata` is present the failure came from the customer's own CRM, usually from validation
  that customer configured. `metadata.originalErrors[].fields` tells you which field to fix.
- 409 means the connection has not finished its initial sync. Wait for
  `system.sync.initial.complete`; do not retry in a tight loop.

## Escalation

`/api/passthrough` will forward an arbitrary authenticated request to the customer's downstream
tenant. It has unbounded blast radius and no schema validation. Do not expose it to an autonomous
agent without a human in the loop — see `agentic-access/vessel-agentic-access.yml`.
