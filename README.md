# Vessel

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Vessel (Kinit Inc.) is a developer-first embedded integrations platform for go-to-market software. It gives a product team one contract to read and write an end customer's CRM, sales engagement, chat, dialer and marketing automation tools, plus a drop-in browser component — Vessel Link — that handles the end user's authorization so the host application never touches downstream credentials. Three modules sit on an open-source integrations library: Unification (one normalized schema per vertical), Actions (typed, validated wrappers over a single provider's native API), and Managed ETL. An /api/passthrough endpoint forwards arbitrary authenticated requests for anything the modules do not cover. Vessel publishes 20 OpenAPI 3.1.0 definitions covering 376 operations in its own documentation repository. As of 2026-08-13 those contracts are still public but the operational surface is not: api.vessel.dev does not answer, api.vessel.land has no DNS record, and both docs.vessel.dev and app.vessel.dev are unreachable.

**Areas:** CRM · Chat · Sales Dialer · Embedded Integrations · Go-To-Market · Integration · iPaaS · Marketing Automation · Sales Engagement · Unified API · Webhook

## Vessel on APIs.io

Everything profiled for Vessel is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/vessel/](https://apis.io/providers/vessel/)** — or go straight to one of the APIs or properties below.

### APIs (37)

- [Vessel Accounts API](https://apis.io/apis/vessel/vessel-accounts-api/) — The accounts API from Vessel — 7 operation(s) for accounts.
- [Vessel Actions API](https://apis.io/apis/vessel/vessel-actions-api/) — The Actions API from Vessel — 115 operation(s) for actions.
- [Vessel Attendees API](https://apis.io/apis/vessel/vessel-attendees-api/) — The attendees API from Vessel — 5 operation(s) for attendees.
- [Vessel Auth API](https://apis.io/apis/vessel/vessel-auth-api/) — The Auth API from Vessel — 6 operation(s) for auth.
- [Vessel Connection API](https://apis.io/apis/vessel/vessel-connection-api/) — The Connection API from Vessel — 1 operation(s) for connection.
- [Vessel Connections API](https://apis.io/apis/vessel/vessel-connections-api/) — The connections API from Vessel — 5 operation(s) for connections.
- [Vessel Contacts API](https://apis.io/apis/vessel/vessel-contacts-api/) — The contacts API from Vessel — 5 operation(s) for contacts.
- [Vessel CRM API](https://apis.io/apis/vessel/vessel-crm-api/) — The Crm API from Vessel — 9 operation(s) for crm.
- [Vessel Deals API](https://apis.io/apis/vessel/vessel-deals-api/) — The deals API from Vessel — 5 operation(s) for deals.
- [Vessel Emails API](https://apis.io/apis/vessel/vessel-emails-api/) — The emails API from Vessel — 5 operation(s) for emails.
- [Vessel Eng Accounts API](https://apis.io/apis/vessel/vessel-engaccounts-api/) — The engAccounts API from Vessel — 2 operation(s) for engaccounts.
- [Vessel Eng Accountss API](https://apis.io/apis/vessel/vessel-engaccountss-api/) — The engAccountss API from Vessel — 1 operation(s) for engaccountss.
- [Vessel Eng Actions API](https://apis.io/apis/vessel/vessel-engactions-api/) — The engActions API from Vessel — 3 operation(s) for engactions.
- [Vessel Eng Calls API](https://apis.io/apis/vessel/vessel-engcalls-api/) — The engCalls API from Vessel — 2 operation(s) for engcalls.
- [Vessel Eng Contacts API](https://apis.io/apis/vessel/vessel-engcontacts-api/) — The engContacts API from Vessel — 3 operation(s) for engcontacts.
- [Vessel Eng Custom Fields API](https://apis.io/apis/vessel/vessel-engcustomfields-api/) — The engCustomFields API from Vessel — 2 operation(s) for engcustomfields.
- [Vessel Eng Dispositions API](https://apis.io/apis/vessel/vessel-engdispositions-api/) — The engDispositions API from Vessel — 1 operation(s) for engdispositions.
- [Vessel Eng Emails API](https://apis.io/apis/vessel/vessel-engemails-api/) — The engEmails API from Vessel — 3 operation(s) for engemails.
- [Vessel Eng Mailboxes API](https://apis.io/apis/vessel/vessel-engmailboxes-api/) — The engMailboxes API from Vessel — 1 operation(s) for engmailboxes.
- [Vessel Eng Passthrough API](https://apis.io/apis/vessel/vessel-engpassthrough-api/) — The engPassthrough API from Vessel — 1 operation(s) for engpassthrough.
- [Vessel Eng Sequences API](https://apis.io/apis/vessel/vessel-engsequences-api/) — The engSequences API from Vessel — 4 operation(s) for engsequences.
- [Vessel Eng Tasks API](https://apis.io/apis/vessel/vessel-engtasks-api/) — The engTasks API from Vessel — 3 operation(s) for engtasks.
- [Vessel Eng Users API](https://apis.io/apis/vessel/vessel-engusers-api/) — The engUsers API from Vessel — 2 operation(s) for engusers.
- [Vessel Events API](https://apis.io/apis/vessel/vessel-events-api/) — The events API from Vessel — 5 operation(s) for events.
- [Vessel Integrations API](https://apis.io/apis/vessel/vessel-integrations-api/) — The integrations API from Vessel — 2 operation(s) for integrations.
- [Vessel Lead Custom Fields API](https://apis.io/apis/vessel/vessel-leadcustomfields-api/) — The leadCustomFields API from Vessel — 1 operation(s) for leadcustomfields.
- [Vessel Leads API](https://apis.io/apis/vessel/vessel-leads-api/) — The leads API from Vessel — 5 operation(s) for leads.
- [Vessel Links API](https://apis.io/apis/vessel/vessel-links-api/) — The links API from Vessel — 1 operation(s) for links.
- [Vessel Lists API](https://apis.io/apis/vessel/vessel-lists-api/) — The lists API from Vessel — 2 operation(s) for lists.
- [Vessel Notes API](https://apis.io/apis/vessel/vessel-notes-api/) — The notes API from Vessel — 5 operation(s) for notes.
- [Vessel Passthrough API](https://apis.io/apis/vessel/vessel-passthrough-api/) — The passthrough API from Vessel — 2 operation(s) for passthrough.
- [Vessel Tasks API](https://apis.io/apis/vessel/vessel-tasks-api/) — The tasks API from Vessel — 5 operation(s) for tasks.
- [Vessel Tokens API](https://apis.io/apis/vessel/vessel-tokens-api/) — The tokens API from Vessel — 1 operation(s) for tokens.
- [Vessel Unifications API](https://apis.io/apis/vessel/vessel-unifications-api/) — The Unifications API from Vessel — 107 operation(s) for unifications.
- [Vessel Users API](https://apis.io/apis/vessel/vessel-users-api/) — The users API from Vessel — 5 operation(s) for users.
- [Vessel Webhooks API](https://apis.io/apis/vessel/vessel-webhooks-api/) — The webhooks API from Vessel — 5 operation(s) for webhooks.
- [Vessel Contact Custom Fields API](https://apis.io/apis/vessel/vessel-contact-custom-fields-api/) — The Contact Custom Fields API from Vessel — 1 operation(s) for contact custom fields.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Vessel Webhooks](https://apis.io/asyncapis/vessel/vessel-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [vessel-mcp.yml](https://apis.io/servers/vessel/vessel-mcp-yml/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Vessel Agentic Access](https://apis.io/agentic-access/vessel/vessel-agentic-access/)

#### JSON Schema (3)

The data models the API reads and writes.

- [Account](https://apis.io/schemas/vessel/vessel-account/)
- [Contact](https://apis.io/schemas/vessel/vessel-contact/)
- [Deal](https://apis.io/schemas/vessel/vessel-deal/)

#### JSON Structure (1)

Data models expressed in JSON Structure.

- [Vessel Contact Structure](https://apis.io/json-structure/vessel/vessel-contact-structure/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Vessel Context](https://apis.io/jsonld/vessel/vessel-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [Vessel Embedded Integrations Vocabulary](https://apis.io/vocabularies/vessel/vessel-vocabulary/)

#### Examples (4)

Example requests and responses.

- [Vessel Get Session Token Example](https://apis.io/examples/vessel/vessel-get-session-token-example/)
- [Vessel List Connections Example](https://apis.io/examples/vessel/vessel-list-connections-example/)
- [Vessel List Crm Contacts Example](https://apis.io/examples/vessel/vessel-list-crm-contacts-example/)
- [Vessel List Integrations Example](https://apis.io/examples/vessel/vessel-list-integrations-example/)

#### Overlays (2)

OpenAPI overlays, including conversational phrasing for each operation.

- [Vessel Crm Overlay](https://apis.io/overlays/vessel/vessel-crm-overlay/)
- [Vessel Platform Overlay](https://apis.io/overlays/vessel/vessel-platform-overlay/)

#### Governance rules (2)

Spectral rulesets for the provider's contracts.

- [Vessel — api rules](https://apis.io/rules/vessel/vessel-api-rules/)
- [Vessel — jsonschema rules](https://apis.io/rules/vessel/vessel-jsonschema-spectral-rules/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Vessel Authentication](https://apis.io/security/vessel/vessel-authentication/)
- [Vessel Domain Security](https://apis.io/security/vessel/vessel-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Vessel Plans Pricing](https://apis.io/plans/vessel/vessel-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Vessel Rate Limits](https://apis.io/rate-limits/vessel/vessel-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Vessel Finops](https://apis.io/finops/vessel/vessel-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.vessel.dev/)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [Getting started](https://github.com/vesselapi/all-api-docs/blob/main/docs/pages/home/getting-started.mdx)
- [API reference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [Pricing](https://www.vessel.dev/pricing)
- [Support](https://www.vessel.dev/contact)
- [Blog](https://www.vessel.dev/blog)
- [Terms of service](https://drive.google.com/file/d/1MAhix9lfQdMW7B600vYeMNtdY3vnQzIQ/view)
- [Privacy policy](https://www.vessel.dev/privacy)
- [GitHub](https://github.com/vesselapi)

## API Evangelist rating

**Kin Score 59.3** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 71.4 |
| Contract quality | 65.3 |
| Contract governance | 45.5 |
| Operational transparency | 50.0 |
| Developer ergonomics | 73.2 |
| Access clarity | 71.1 |

**Agent readiness 32.2** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | — |

**Regulatory alignment 29.4** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/vessel/](https://apis.io/providers/vessel/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Vessel: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/vessel/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
