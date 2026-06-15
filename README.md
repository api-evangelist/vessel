# Vessel (vessel)

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
