# Vessel (vessel)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Vessel (Kinit Inc.) is a developer-first embedded integrations platform for go-to-market software. It gives a product team one contract to read and write an end customer's CRM, sales engagement, chat, dialer and marketing automation tools, plus a drop-in browser component — Vessel Link — that handles the end user's authorization so the host application never touches downstream credentials. Three modules sit on an open-source integrations library: Unification (one normalized schema per vertical), Actions (typed, validated wrappers over a single provider's native API), and Managed ETL. An /api/passthrough endpoint forwards arbitrary authenticated requests for anything the modules do not cover. Vessel publishes 20 OpenAPI 3.1.0 definitions covering 376 operations in its own documentation repository. As of 2026-08-13 those contracts are still public but the operational surface is not: api.vessel.dev does not answer, api.vessel.land has no DNS record, and both docs.vessel.dev and app.vessel.dev are unreachable.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- CRM
- Chat
- Dialer
- Embedded Integrations
- GTM
- Integrations
- iPaaS
- Marketing Automation
- Sales Engagement
- Unified API
- Webhooks

## Timestamps

- **Created:** 2026-05-03
- **Modified:** 2026-08-13

## Contracts

20 OpenAPI 3.1.0 definitions covering 376 operations, harvested 2026-08-13 from Vessel's own documentation repository, [https://github.com/vesselapi/all-api-docs](https://github.com/vesselapi/all-api-docs), where they are enumerated in `docs/mint.json`.

> **Note.** The rendered documentation site `docs.vessel.dev` returns HTTP 404, and neither `api.vessel.dev` nor `api.vessel.land` answered a connection on 2026-08-13. The contracts below remain publicly readable; the APIs they describe are not currently reachable. See [`lifecycle/vessel-lifecycle.yml`](lifecycle/vessel-lifecycle.yml).

## APIs

### Vessel Platform API

The Vessel Platform API is the control plane of the Vessel embedded integrations platform. It covers the Link authentication handshake (session tokens and access tokens), the catalog of supported integrations, connection lifecycle (list, find, delete), customer-managed OAuth apps, the /api/passthrough escape hatch for calling a downstream provider's native API directly, and webhook subscription management. Every request is authenticated with an x-vessel-api-token header. Published by Vessel as OpenAPI 3.1.0 with 15 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Authentication
- Connections
- Integrations
- Passthrough
- Platform
- Webhooks

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-platform-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel CRM Unified API

The Vessel CRM Unified API (v2) normalizes CRM objects across Salesforce, HubSpot, Zoho, Pipedrive, Close, Freshsales, Microsoft Dynamics, Affinity and monday.com behind a single schema under /api/unifications/crm. It exposes list, find, batch-read, create, update and details operations for users, contacts, deals, accounts, leads, notes, tasks, events, emails, calls and lists. Published by Vessel as OpenAPI 3.1.0 with 69 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- CRM
- Contacts
- Deals
- Leads
- Normalized
- Unified API

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-crm-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel Sales Engagement Unified API

The Vessel Sales Engagement Unified API normalizes sales engagement objects across Outreach, Salesloft, Apollo and similar tools under /api/unifications/engagement, covering users, contacts, accounts, sequences, tasks, calls, emails and mailboxes behind one schema. Published by Vessel as OpenAPI 3.1.0 with 20 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Sales Engagement
- Sequences
- Unified API
- Outreach
- Salesloft

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-engagement-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel Chat Unified API

The Vessel Chat Unified API normalizes chat platform objects across Slack and Microsoft Teams under /api/unifications/chat, providing a single interface for channels, messages and users. Published by Vessel as OpenAPI 3.1.0 with 4 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Chat
- Slack
- Microsoft Teams
- Unified API
- Messaging

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-chat-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel Dialer Unified API

The Vessel Dialer Unified API normalizes telephony/dialer objects across Aircall, Dialpad and RingCentral under /api/unifications/dialer, covering calls, call recordings, users and contacts. Published by Vessel as OpenAPI 3.1.0 with 9 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Dialer
- Telephony
- Calls
- Aircall
- Unified API

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-dialer-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel Marketing Automation Unified API

The Vessel Marketing Automation Unified API normalizes marketing automation objects across Mailchimp, ActiveCampaign and Customer.io under /api/unifications/marketing, covering lists, contacts, campaigns and subscriptions. Published by Vessel as OpenAPI 3.1.0 with 7 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Marketing Automation
- Mailchimp
- Campaigns
- Unified API
- Email

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-marketing-automation-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel CRM API (v1, legacy)

The first-generation Vessel CRM API, published under /crm/* with the vessel-api-token header and an accessToken query/body parameter. Superseded by the v2 unified CRM API under /api/unifications/crm and marked as hidden/legacy in Vessel's own documentation navigation, but still published as a full OpenAPI 3.1 contract with search, batch and custom-field operations the v2 surface does not carry. Published by Vessel as OpenAPI 3.1.0 with 93 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.land`

#### Tags

- CRM
- Legacy
- v1
- Search
- Batch

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-crm-v1-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel Engagement API (v1, legacy)

The first-generation Vessel Sales Engagement API, published under /engagement/* on api.vessel.land. Covers users, accounts, contacts, tasks, actions, calls, emails, call dispositions, sequences, sequence steps and mailboxes, plus the Link and connection endpoints. Superseded by the v2 engagement unification surface. Published by Vessel as OpenAPI 3.1.0 with 44 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.land`

#### Tags

- Sales Engagement
- Legacy
- v1
- Sequences
- Mailboxes

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-engagement-v1-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel Salesforce Actions API

The Vessel Actions API for Salesforce — typed, validated wrappers over Salesforce's native API served under /api/actions/salesforce. Actions add request/response schema validation, standardized data types and normalized error handling on top of the downstream provider, so callers do not have to absorb that provider's quirks directly. Published by Vessel as OpenAPI 3.1.0 with 10 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Actions
- CRM
- Salesforce
- Integrations
- Validation

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-salesforce-actions-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel Slack Actions API

The Vessel Actions API for Slack — typed, validated wrappers over Slack's native API served under /api/actions/slack. Actions add request/response schema validation, standardized data types and normalized error handling on top of the downstream provider, so callers do not have to absorb that provider's quirks directly. Published by Vessel as OpenAPI 3.1.0 with 4 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Actions
- Chat
- Slack
- Integrations
- Validation

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-slack-actions-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel Microsoft Teams Actions API

The Vessel Actions API for Microsoft Teams — typed, validated wrappers over Microsoft Teams's native API served under /api/actions/teams. Actions add request/response schema validation, standardized data types and normalized error handling on top of the downstream provider, so callers do not have to absorb that provider's quirks directly. Published by Vessel as OpenAPI 3.1.0 with 4 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Actions
- Chat
- Microsoft Teams
- Integrations
- Validation

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-teams-actions-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel Outreach Actions API

The Vessel Actions API for Outreach — typed, validated wrappers over Outreach's native API served under /api/actions/outreach. Actions add request/response schema validation, standardized data types and normalized error handling on top of the downstream provider, so callers do not have to absorb that provider's quirks directly. Published by Vessel as OpenAPI 3.1.0 with 17 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Actions
- Sales Engagement
- Outreach
- Integrations
- Validation

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-outreach-actions-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel Salesloft Actions API

The Vessel Actions API for Salesloft — typed, validated wrappers over Salesloft's native API served under /api/actions/salesloft. Actions add request/response schema validation, standardized data types and normalized error handling on top of the downstream provider, so callers do not have to absorb that provider's quirks directly. Published by Vessel as OpenAPI 3.1.0 with 14 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Actions
- Sales Engagement
- Salesloft
- Integrations
- Validation

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-salesloft-actions-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel Apollo Actions API

The Vessel Actions API for Apollo — typed, validated wrappers over Apollo's native API served under /api/actions/apollo. Actions add request/response schema validation, standardized data types and normalized error handling on top of the downstream provider, so callers do not have to absorb that provider's quirks directly. Published by Vessel as OpenAPI 3.1.0 with 23 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Actions
- Sales Engagement
- Apollo
- Integrations
- Validation

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-apollo-actions-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel Aircall Actions API

The Vessel Actions API for Aircall — typed, validated wrappers over Aircall's native API served under /api/actions/aircall. Actions add request/response schema validation, standardized data types and normalized error handling on top of the downstream provider, so callers do not have to absorb that provider's quirks directly. Published by Vessel as OpenAPI 3.1.0 with 9 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Actions
- Dialer
- Aircall
- Integrations
- Validation

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-aircall-actions-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel Dialpad Actions API

The Vessel Actions API for Dialpad — typed, validated wrappers over Dialpad's native API served under /api/actions/dialpad. Actions add request/response schema validation, standardized data types and normalized error handling on top of the downstream provider, so callers do not have to absorb that provider's quirks directly. Published by Vessel as OpenAPI 3.1.0 with 9 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Actions
- Dialer
- Dialpad
- Integrations
- Validation

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-dialpad-actions-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel RingCentral Actions API

The Vessel Actions API for RingCentral — typed, validated wrappers over RingCentral's native API served under /api/actions/ringcentral. Actions add request/response schema validation, standardized data types and normalized error handling on top of the downstream provider, so callers do not have to absorb that provider's quirks directly. Published by Vessel as OpenAPI 3.1.0 with 9 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Actions
- Dialer
- RingCentral
- Integrations
- Validation

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-ringcentral-actions-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel Mailchimp Actions API

The Vessel Actions API for Mailchimp — typed, validated wrappers over Mailchimp's native API served under /api/actions/mailchimp. Actions add request/response schema validation, standardized data types and normalized error handling on top of the downstream provider, so callers do not have to absorb that provider's quirks directly. Published by Vessel as OpenAPI 3.1.0 with 5 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Actions
- Marketing Automation
- Mailchimp
- Integrations
- Validation

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-mailchimp-actions-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel ActiveCampaign Actions API

The Vessel Actions API for ActiveCampaign — typed, validated wrappers over ActiveCampaign's native API served under /api/actions/activecampaign. Actions add request/response schema validation, standardized data types and normalized error handling on top of the downstream provider, so callers do not have to absorb that provider's quirks directly. Published by Vessel as OpenAPI 3.1.0 with 7 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Actions
- Marketing Automation
- ActiveCampaign
- Integrations
- Validation

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-activecampaign-actions-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

### Vessel monday.com Actions API

The Vessel Actions API for monday.com — typed, validated wrappers over monday.com's native API served under /api/actions/monday. Actions add request/response schema validation, standardized data types and normalized error handling on top of the downstream provider, so callers do not have to absorb that provider's quirks directly. Published by Vessel as OpenAPI 3.1.0 with 4 operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)
- **Base URL:** `https://api.vessel.dev`

#### Tags

- Actions
- Work Management
- monday.com
- Integrations
- Validation

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-monday-actions-openapi.yml)
- [Documentation](https://github.com/vesselapi/all-api-docs)
- [APIReference](https://github.com/vesselapi/all-api-docs/tree/main/docs/pages)
- [GitHubRepository](https://github.com/vesselapi/all-api-docs)
- [SpectralRuleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)

## Artifacts

**Contracts**

- `Overlay` — [overlays/vessel-crm-overlay.yaml](overlays/vessel-crm-overlay.yaml)
- `Examples` — [examples/vessel-list-crm-contacts-example.json](examples/vessel-list-crm-contacts-example.json)
- `Vocabulary` — [vocabulary/vessel-vocabulary.yml](vocabulary/vessel-vocabulary.yml)
- `SpectralRuleset` — [rules/vessel-api-rules.yml](rules/vessel-api-rules.yml)
- `JSONSchema` — [json-schema/vessel-contact-schema.json](json-schema/vessel-contact-schema.json)
- `JSONSchema` — [json-schema/vessel-deal-schema.json](json-schema/vessel-deal-schema.json)
- `JSONSchema` — [json-schema/vessel-account-schema.json](json-schema/vessel-account-schema.json)
- `JSONStructure` — [json-structure/vessel-contact-structure.json](json-structure/vessel-contact-structure.json)
- `JSONLD` — [json-ld/vessel-context.jsonld](json-ld/vessel-context.jsonld)
- `Overlay` — [overlays/vessel-platform-overlay.yaml](overlays/vessel-platform-overlay.yaml)
- `SpectralRuleset` — [rules/vessel-jsonschema-spectral-rules.yml](rules/vessel-jsonschema-spectral-rules.yml)

**Runtime semantics**

- `ErrorCatalog` — [errors/vessel-error-codes.yml](errors/vessel-error-codes.yml)
- `Lifecycle` — [lifecycle/vessel-lifecycle.yml](lifecycle/vessel-lifecycle.yml)
- `Conventions` — [conventions/vessel-conventions.yml](conventions/vessel-conventions.yml)
- `DataModel` — [data-model/vessel-data-model.yml](data-model/vessel-data-model.yml)
- `Webhooks` — [asyncapi/vessel-webhooks.yml](asyncapi/vessel-webhooks.yml)
- `RateLimits` — [rate-limits/vessel-rate-limits.yml](rate-limits/vessel-rate-limits.yml)

**Access + security**

- `AgenticAccess` — [agentic-access/vessel-agentic-access.yml](agentic-access/vessel-agentic-access.yml)
- `DomainSecurity` — [security/vessel-domain-security.yml](security/vessel-domain-security.yml)
- `Authentication` — [authentication/vessel-authentication.yml](authentication/vessel-authentication.yml)
- `Conformance` — [conformance/vessel-conformance.yml](conformance/vessel-conformance.yml)
- `Sandbox` — [sandbox/vessel-sandbox.yml](sandbox/vessel-sandbox.yml)

**Agent surface**

- `LLMsTxt` — [llms/vessel-llms.txt](llms/vessel-llms.txt)
- `AgentSkill` — [skills/_index.yml](skills/_index.yml)

**Commercial**

- `Packages` — [packages/vessel-packages.yml](packages/vessel-packages.yml)
- `Components` — [components/vessel-components.yml](components/vessel-components.yml)
- `Plans` — [plans/vessel-plans-pricing.yml](plans/vessel-plans-pricing.yml)
- `FinOps` — [finops/vessel-finops.yml](finops/vessel-finops.yml)

## Links

- **LinkedIn**: https://www.linkedin.com/company/vesselapi
- **Website**: https://www.vessel.dev/
- **Integrations**: https://www.vessel.dev/integrations
- **GitHubOrganization**: https://github.com/vesselapi
- **GitHubRepository**: https://github.com/vesselapi/integrations
- **SDKs**: https://github.com/vesselapi/client-sdk
- **SDKs**: https://www.npmjs.com/package/@vesselapi/sdk
- **SDKs**: https://www.npmjs.com/package/@vesselapi/react-vessel-link
- **Blog**: https://www.vessel.dev/blog
- **Documentation**: https://github.com/vesselapi/all-api-docs
- **APIReference**: https://github.com/vesselapi/all-api-docs/tree/main/docs/pages
- **GettingStarted**: https://github.com/vesselapi/all-api-docs/blob/main/docs/pages/home/getting-started.mdx
- **Pricing**: https://www.vessel.dev/pricing
- **PrivacyPolicy**: https://www.vessel.dev/privacy
- **TermsOfService**: https://drive.google.com/file/d/1MAhix9lfQdMW7B600vYeMNtdY3vnQzIQ/view
- **Support**: https://www.vessel.dev/contact
- **Roadmap**: https://vesselapi.canny.io/
