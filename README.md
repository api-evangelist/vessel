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

Vessel is a developer-first embedded integrations platform that enables product teams to add native integrations to their applications. It provides unified API abstractions, actions APIs, and passthrough APIs to connect with CRM, sales engagement, marketing automation, chat, and dialer tools while managing authentication, rate limits, and data normalization. The platform supports OAuth and API-key authentication via a drop-in React UI component (Vessel Link), with two API surfaces: api.vessel.dev for the newer GTM integrations platform and api.vessel.land for the CRM-focused platform.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- CRM
- Embedded Integrations
- GTM
- Integrations
- iPaaS
- Sales Engagement
- Unified API

## Timestamps

- **Created:** 2026-05-03
- **Modified:** 2026-05-19

## APIs

### Vessel Platform API

The Vessel Platform API (api.vessel.dev) provides the core integration platform capabilities including authentication session management, access token exchange, connection lifecycle management, integration listing, passthrough API calls, and webhook management. Authentication uses the x-vessel-api-token header for server-side requests plus x-vessel-access-token for user connection scoped operations.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)

#### Tags

- Authentication
- Connections
- Integrations
- Passthrough
- Webhooks

#### Properties

- [Documentation](https://docs.vessel.dev/)
- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-platform-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Spectral Ruleset](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/rules/vessel-api-rules.yml)
- [GitHub Repository](https://github.com/vesselapi/all-api-docs)
- [Postman Collection](collections/vessel-crm.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vessel-crm.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/vessel-platform.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vessel-platform.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Vessel CRM API

The Vessel CRM API (api.vessel.land) provides unified CRM operations across Salesforce, HubSpot, Zoho, Pipedrive, Close, Freshsales, Microsoft Dynamics, Affinity, monday.com, and Freshdesk. The API normalizes contacts, deals, accounts, leads, notes, tasks, emails, calls, events, event attendees, users, and lists. Authentication uses vessel-api-token header and accessToken query parameter.

- **Human URL:** [https://www.vessel.dev/unified-apis/crm](https://www.vessel.dev/unified-apis/crm)

#### Tags

- Accounts
- CRM
- Contacts
- Deals
- Leads
- Unified API

#### Properties

- [Documentation](https://docs.vessel.dev/)
- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/openapi/vessel-crm-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [JSON Schema](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/json-schema/vessel-contact-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [GitHub Repository](https://github.com/vesselapi/all-api-docs)
- [Postman Collection](collections/vessel-crm.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vessel-crm.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/vessel-platform.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vessel-platform.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Vessel Actions API

The Vessel Actions API provides pre-built, validated actions for common integration operations across CRM, sales engagement, marketing automation, chat, and dialer systems. Actions validate API responses and request inputs, standardize data types (ISO dates, string IDs), and abstract downstream provider quirks.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)

#### Tags

- Actions
- Automation
- Integrations
- Validation

#### Properties

- [Documentation](https://www.vessel.dev/)
- [GitHub Repository](https://github.com/vesselapi/integrations)
- [Postman Collection](collections/vessel-crm.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vessel-crm.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/vessel-platform.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vessel-platform.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Vessel Unified API

The Vessel Unified API provides a standardized interface across integrations, abstracting away the differences between third-party APIs to provide a consistent developer experience. Supports CRM, sales engagement, chat, marketing automation, and dialer categories.

- **Human URL:** [https://www.vessel.dev/](https://www.vessel.dev/)

#### Tags

- CRM
- Chat
- Dialers
- Marketing Automation
- Normalized
- Sales Engagement
- Unified API

#### Properties

- [Documentation](https://www.vessel.dev/)
- [Postman Collection](collections/vessel-crm.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vessel-crm.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/vessel-platform.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vessel-platform.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/vesselapi)
- [Website](https://www.vessel.dev/)
- [Documentation](https://docs.vessel.dev/)
- [Integrations](https://www.vessel.dev/integrations)
- [GitHub Organization](https://github.com/vesselapi)
- [GitHub Repository](https://github.com/vesselapi/integrations)
- [SDK](https://github.com/vesselapi/client-sdk)
- [SDK](https://www.npmjs.com/package/@vesselapi/sdk)
- [SDK](https://www.npmjs.com/package/@vesselapi/react-vessel-link)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
