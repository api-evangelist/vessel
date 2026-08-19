---
name: vessel-subscribe-to-change-events
description: >-
  Register a Vessel webhook and consume its events correctly — verify the signature, survive
  at-least-once delivery, and avoid the silent failure where a webhook is registered but no events
  ever arrive because the objects were never synced.
api: vessel:platform-api
spec: openapi/vessel-platform-openapi.yml
operations:
  - create-webhook
  - list-webhooks
  - find-webhook
  - delete-webhook
  - get-one-session-token
generated: '2026-08-13'
method: generated
source: openapi/vessel-platform-openapi.yml + https://github.com/vesselapi/all-api-docs/blob/main/docs/pages/home/webhooks.mdx
---

# Subscribe to change events

## The precondition that makes or breaks this

**Webhooks fire only for objects enabled in the synced-cache.** Vessel puts this in bold in its own
docs. Register a webhook against connections whose objects were never synced and you get a healthy
looking subscription that emits nothing, forever, with no error anywhere. The sync set is chosen at
connection time under `connection.sync.objects` in `get-one-session-token` — so this skill's real
first step happens back in `vessel-connect-a-customer-account`.

## Steps

1. **Register once per project.**
   `POST /webhooks/create` (`create-webhook`) with `{"url": "https://yourapp.example/webhooks/vessel"}`.
   Subscriptions are per project (per API key), not per connection: registering one immediately starts
   delivery for every existing connection on that project, and covers new connections automatically.
   You do not add a webhook per connection.

2. **Verify the signature on every delivery.** Vessel sends four headers:
   `x-vessel-project-id`, `x-vessel-timestamp`, `x-vessel-webhook-id`, `x-vessel-webhook-signature`.
   The signature is published as:

   ```js
   const hash = (s) => crypto.createHash("sha256").update(s).digest("hex");
   const expected = hash(`${process.env.VESSEL_API_TOKEN}:${timestamp}:${JSON.stringify(body)}`);
   ```

   Note what this is: a plain SHA-256 over a concatenation, not an HMAC, and the shared secret is your
   long-lived API token rather than a dedicated webhook secret. Compare in constant time, and treat a
   leaked webhook signature as information about your API token. Re-serializing the body must produce
   the exact bytes Vessel hashed, so verify against the raw request body.

3. **Return 2xx fast.** Non-2xx triggers up to 3 redeliveries. Acknowledge, enqueue, process
   asynchronously — do not do the downstream read inside the webhook handler.

4. **Branch on `eventType`.** Two shapes:

   - `system.sync.initial.complete` — the connection has finished its first pull. This is the signal
     that clears the 409 "Data still syncing" state. Gate your first reads on it.
   - `object.crm.{object}.{created|updated|deleted}` — e.g. `object.crm.deals.deleted`. Vessel does
     not publish a closed enumeration of these, so parse defensively and ignore what you do not know.

5. **Expect an id, not a record.** Object events carry only `data.id`. Every event you care about
   costs a follow-up read (`get-contact`, `get-deal`, …) — budget for that, especially on a bulk
   change in the customer's CRM.

6. **De-duplicate on `eventId`.** Delivery is at-least-once by construction (3 retries, no exactly-once
   guarantee). Keep a short-lived seen-set.

7. **Audit and clean up.** `list-webhooks` / `find-webhook` to inspect, `delete-webhook` to remove.
   Webhooks are also visible in the Vessel dashboard's webhooks tab.

## Latency expectations

Real-time only where the downstream platform has native webhook support. Otherwise events are emitted
after the next sync, and syncs run hourly — so worst case an external change is visible up to an hour
late. Changes made *through* the Vessel API update the cache immediately.

## Known gaps

No AsyncAPI, no event-type registry, no delivery-attempt log and no replay endpoint. If you miss a
window of events, reconciliation means a full re-read, not a replay. See
`asyncapi/vessel-webhooks.yml`.
