# Vessel

Vessel is a developer-first embedded integrations platform that enables product teams to add native integrations to their applications. It provides unified API abstractions, actions APIs, and passthrough APIs to connect with CRM, sales engagement, marketing automation, chat, and dialer tools while managing authentication, rate limits, and data normalization.

**URL:** [https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/vessel/refs/heads/main/apis.yml)

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
- **Modified:** 2026-05-03

## APIs

### Vessel Platform API (api.vessel.dev)

The newer Vessel platform providing session management, access token exchange, connection lifecycle, integration catalog, passthrough, and webhooks.

Authentication: `x-vessel-api-token` header (server) + `x-vessel-access-token` header (user-scoped)

- **Documentation:** [https://docs.vessel.dev/](https://docs.vessel.dev/)
- **OpenAPI Spec:** [openapi/vessel-platform-openapi.yml](openapi/vessel-platform-openapi.yml)
- **API Docs Repository:** [https://github.com/vesselapi/all-api-docs](https://github.com/vesselapi/all-api-docs)

### Vessel CRM API (api.vessel.land)

Unified CRM API providing normalized contacts, deals, accounts, leads, notes, tasks, emails, calls, events, and users across Salesforce, HubSpot, Zoho, Pipedrive, Close, Freshsales, Microsoft Dynamics, Affinity, and monday.com.

Authentication: `vessel-api-token` header + `accessToken` query parameter

- **Documentation:** [https://docs.vessel.dev/](https://docs.vessel.dev/)
- **OpenAPI Spec:** [openapi/vessel-crm-openapi.yml](openapi/vessel-crm-openapi.yml)

### Supported Integrations

| Category | Tools |
|----------|-------|
| CRM | Salesforce, HubSpot, Zoho, Pipedrive, Close, Freshsales, Microsoft Dynamics, Affinity, monday.com, Freshdesk |
| Sales Engagement | Outreach, Apollo, Salesloft |
| Chat | Slack, Microsoft Teams |
| Marketing Automation | Customer.io, Mailchimp, ActiveCampaign |
| Dialer | Aircall, Dialpad, RingCentral |

## Authentication Flow

1. Backend calls `POST /auth/session-token` to get a session token
2. Frontend opens the Vessel modal using `@vesselapi/client-sdk` with the session token
3. User authenticates their integration via OAuth modal
4. On success, backend calls `POST /auth/access-token` to exchange session token for a permanent access token
5. Access token is stored securely and used for all subsequent API calls via `x-vessel-access-token` header

## Artifacts

### OpenAPI Specifications

| Spec | Description |
|------|-------------|
| [openapi/vessel-platform-openapi.yml](openapi/vessel-platform-openapi.yml) | Vessel Platform API — auth, connections, integrations, passthrough, webhooks |
| [openapi/vessel-crm-openapi.yml](openapi/vessel-crm-openapi.yml) | Vessel CRM API — contacts, deals, accounts, leads, notes, tasks, users |

### Capabilities (Naftiko)

| File | Description |
|------|-------------|
| [capabilities/crm-integration.yaml](capabilities/crm-integration.yaml) | Unified CRM integration workflow — 10 tools for contacts, deals, accounts, leads, notes, tasks |
| [capabilities/shared/vessel-crm.yaml](capabilities/shared/vessel-crm.yaml) | Shared Vessel CRM API consumed definition |

### Spectral Rules

| File | Description |
|------|-------------|
| [rules/vessel-api-rules.yml](rules/vessel-api-rules.yml) | Spectral ruleset enforcing Vessel API conventions |

### JSON Schemas

| Schema | Description |
|--------|-------------|
| [json-schema/vessel-contact-schema.json](json-schema/vessel-contact-schema.json) | CRM contact entity schema |
| [json-schema/vessel-deal-schema.json](json-schema/vessel-deal-schema.json) | CRM deal entity schema |

### JSON Structures

| Structure | Description |
|-----------|-------------|
| [json-structure/vessel-contact-structure.json](json-structure/vessel-contact-structure.json) | Contact field structure documentation |

### JSON-LD

| File | Description |
|------|-------------|
| [json-ld/vessel-context.jsonld](json-ld/vessel-context.jsonld) | JSON-LD context mapping Vessel CRM vocabulary to schema.org |

### Examples

| Example | Description |
|---------|-------------|
| [examples/vessel-create-session-token-example.json](examples/vessel-create-session-token-example.json) | Create authentication session token |
| [examples/vessel-get-all-contacts-example.json](examples/vessel-get-all-contacts-example.json) | Get all CRM contacts |
| [examples/vessel-list-integrations-example.json](examples/vessel-list-integrations-example.json) | List all supported integrations |

### Vocabulary

| File | Description |
|------|-------------|
| [vocabulary/vessel-vocabulary.yml](vocabulary/vessel-vocabulary.yml) | Embedded integrations and CRM domain vocabulary |

## Common Properties

- [Website](https://www.vessel.dev/)
- [API Documentation](https://docs.vessel.dev/)
- [Integrations Catalog](https://www.vessel.dev/integrations)
- [GitHub Organization](https://github.com/vesselapi)
- [Integrations Library](https://github.com/vesselapi/integrations)
- [Client SDK](https://github.com/vesselapi/client-sdk)
- [Node.js SDK (npm)](https://www.npmjs.com/package/@vesselapi/sdk)
- [React Link Component (npm)](https://www.npmjs.com/package/@vesselapi/react-vessel-link)

## Maintainers

**Kin Lane** — kin@apievangelist.com
