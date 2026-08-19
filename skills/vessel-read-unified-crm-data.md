---
name: vessel-read-unified-crm-data
description: >-
  Page through a customer's CRM objects through Vessel's unified v2 API — contacts, deals, accounts,
  leads, notes, tasks, events, emails, calls — with cursor pagination, filters and the $native escape
  hatch, without exhausting the customer's downstream rate limits.
api: vessel:crm-unified-api
spec: openapi/vessel-crm-openapi.yml
operations:
  - get-info
  - list-contacts
  - get-contact
  - batch-read-contacts
  - get-details-crm-contact
  - list-deals
  - list-accounts
  - list-leads
generated: '2026-08-13'
method: generated
source: openapi/vessel-crm-openapi.yml + https://github.com/vesselapi/all-api-docs/blob/main/docs/pages/home/synced-cache.mdx
---

# Read unified CRM data

One shape of call works across Salesforce, HubSpot, Zoho, Pipedrive, Close, Freshsales, Dynamics,
Affinity and monday.com.

## The single thing that trips people up

**Reads are POSTs.** `POST /api/unifications/crm/contacts/list` is a read. There is no GET anywhere on
the v2 surface, because filters, includes and synced-cache selectors travel in the request body. If
you are building an agent policy that gates writes by HTTP verb, it will misclassify every Vessel read
as a write. Gate on the path verb suffix (`/list`, `/find`, `/batch-read`, `/details` are reads;
`/create`, `/update` are writes) or on the operationId prefix.

## Steps

1. **Check what this connection can actually do.**
   `POST /api/unifications/crm/info/find` (`get-info`) with the `accessToken`. Different downstream
   CRMs implement different subsets — calling an operation the connected CRM does not support comes
   back as a 5xx, not a 501.

2. **Page a collection.**
   `POST /api/unifications/crm/contacts/list` (`list-contacts`) with `{"accessToken": "...",
   "cursor": null}`. Read `nextPageCursor` off the response and send it back as `cursor` until it is
   absent. There is no page-size parameter and no total count.

   The same pattern holds for `list-deals`, `list-accounts`, `list-leads`, `list-notes`, `list-tasks`,
   `list-events`, `list-emails`, `list-calls`, `list-users`, `list-lists`.

3. **Narrow with `filters`, but check the caveat.**
   `filters` supports `StringFilter`, `StringListFilter`, `NumberFilter`, `BooleanFilter` and
   `DateFilter`. Most fields are annotated **"Requires enabling Synced-cache"** in the spec — the
   filter runs against Vessel's cache, not the downstream API. If synced-cache is off for that object,
   the filter has no backing store. `email` is the one contact filter that does not carry the caveat.

4. **Fetch specific records.**
   `get-contact` for one by id; `batch-read-contacts` for a set of ids in one call. Prefer batch-read
   over a loop of `find` calls — without synced-cache each call hits the customer's CRM directly and
   spends their rate limit.

5. **Reach fields Vessel does not unify.**
   Every returned object carries `$native` with the untranslated record from the source system. For
   the source system's field metadata use `get-details-crm-contact`. Note that `/details` responses
   are the one thing Vessel documents as *not* synced to the cache.

6. **Walk relationships.**
   Relationships live in `associations` — `accountIds`, `dealIds`, `leadIds`, `ownerUserId` on a
   Contact, and so on. They are only bidirectional when **both** objects are synced: sync Deals but
   not Tasks and the task ids may simply be absent. See `data-model/vessel-data-model.yml`.

## Rate limits

Vessel publishes no numeric limits and returns no rate-limit headers; the marketing site says
"unlimited API calls". The real ceiling is the **customer's** downstream quota, which you spend on
every uncached read. For read-heavy work — scanning a whole CRM — enable synced-cache at connection
time; Vessel states synced reads carry no read rate limits because they hit a Vessel database.

Downstream 429s are normalized into the Vessel error envelope with the original payload under
`metadata.originalErrors`, not surfaced as a `Retry-After` header.
