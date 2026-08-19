---
name: vessel-connect-a-customer-account
description: >-
  Run the Vessel Link handshake end to end so an end customer authorizes one of their GTM tools and
  your server ends up holding a durable per-connection accessToken.
api: vessel:platform-api
spec: openapi/vessel-platform-openapi.yml
operations:
  - get-all-integrations
  - get-one-session-token
  - get-one-access-token
  - get-all-connections
generated: '2026-08-13'
method: generated
source: openapi/vessel-platform-openapi.yml + https://github.com/vesselapi/all-api-docs/blob/main/docs/pages/crm/authentication-and-security.mdx
---

# Connect a customer account (Vessel Link)

Vessel's own analogy: the project API token gets you into the gated neighborhood; each customer's
account is a locked house with its own key. This skill gets you that key.

**Before you start.** The API host `api.vessel.dev` did not answer on 2026-08-13 and there is no
reachable way to obtain an API token (`app.vessel.dev` does not respond; the documented route is
emailing support@vessel.dev). Treat this skill as a description of the published contract.

## Preconditions

- A project API token. Send it as `x-vessel-api-token` on every call to `api.vessel.dev`.
  On the legacy `api.vessel.land` surface the header is `vessel-api-token` — no `x-` prefix.
- A browser context that can render the Vessel Link modal (`@vesselapi/react-vessel-link`, or the
  framework-agnostic `client-sdk`).

## Steps

1. **List what the customer can connect.**
   `POST /api/integrations/list` (`get-all-integrations`). Body is optional; pass
   `{"filters": {"ids": ["salesforce", "hubspot"]}}` to narrow it. The response gives you
   `integrationId`, a display name and a logo URI for each integration — enough to render your own
   picker.

2. **Mint a session token, server-side.**
   `POST /api/auth/session-token` (`get-one-session-token`). Pass `integrationId` when the connection
   should use the synced-cache, and set the objects to sync under `connection.sync.objects`.
   Returns `{"sessionToken": "v_session_..."}`.

   Decide the sync set here. It is not just a performance choice: **webhooks fire only for objects in
   the synced-cache**, and most `filters` on the unified read operations are annotated "Requires
   enabling Synced-cache". Skipping this leaves you with an integration that neither filters nor
   notifies.

3. **Hand the session token to the browser.** The Link component walks the user through the
   downstream provider's own OAuth screen. Never ship the project API token to the browser — the
   session token exists precisely so you do not have to.

4. **Take the publicToken from `onSuccess`** and send it to your server. It is short-lived; an expired
   one comes back as a 400 "Public token expired".

5. **Exchange it for the durable credential.**
   `POST /api/auth/access-token` (`get-one-access-token`) with the publicToken. Store the returned
   `accessToken` encrypted, keyed by your own customer id. This is a permanent credential for one
   customer's one connected account.

6. **Confirm the connection landed.**
   `POST /api/connections/list` (`get-all-connections`) and check the connection state.

## After connecting

- If synced-cache is on, the connection is not usable immediately. Calls against it return
  **409 "Data still syncing"** until Vessel finishes the initial pull. Wait for the
  `system.sync.initial.complete` webhook rather than polling.
- Every subsequent unified or actions call needs BOTH credentials: the project token in the header and
  the `accessToken` in the request body.

## Failure modes to code for

| What you see | What it means | What to do |
|---|---|---|
| 401 | Invalid API token, link token, or access token | Check you are using the right header name for the host you are calling |
| 400 "Maximum number of connections reached for development account" | Development keys cap at 5 connections | Delete unused development connections, or use the production key |
| 400 "Public token expired" | Too long between `onSuccess` and the exchange | Restart the Link flow |
| 5xx with an `errorCode` | Vessel returns some validation failures as 5xx by design | Read `message`/`errorCode` before retrying — a blind 5xx retry loop will spin forever |

See `errors/vessel-error-codes.yml` and `conventions/vessel-conventions.yml`.
