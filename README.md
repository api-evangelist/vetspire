# Vetspire (vetspire)

Vetspire is a cloud-based, AI-enabled veterinary practice management (PIMS) platform for animal hospitals and clinics, covering electronic medical records, scheduling, client communications, billing, inventory, labs, and reminders. Vetspire exposes a single public **GraphQL API** at `https://api.vetspire.com/graphql` - every action in the product is powered by GraphQL - authenticated with an `Authorization` API token and organized by veterinary practice domains. The schema exposes 400+ object types, 248 input objects, and 112 enums, with a maximum query depth of 8.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/vetspire/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/vetspire/refs/heads/main/apis.yml)

## Tags

- Veterinary
- Practice Management
- PIMS
- Healthcare
- GraphQL
- Electronic Medical Records
- Scheduling

## Timestamps

- **Created:** 2026-07-04
- **Modified:** 2026-07-04

## API

Vetspire's public API is a single GraphQL endpoint. The catalog below lists the logical APIs as GraphQL operation groups by domain. All share the base URL `https://api.vetspire.com/graphql` and require an `Authorization` API token.

| API | Domain | Description |
| --- | --- | --- |
| Accounts & Clients API | Accounts | Search/read/create clients (pet owners), balances, linked patients. |
| Patients API | Clinical | Patient (animal) records - species, breed, weight, microchip, alerts. |
| Schedule & Appointments API | Schedule | Appointments for a location/date range, provider schedules. |
| Encounters & Clinical Records API | Clinical / Treatment | Encounters (SOAP notes), treatment sheets, immunizations, prescriptions. |
| Billing & Invoices API | Billing / New Billing | Invoices, line items, orders, payments, AR balances. |
| Inventory & Products API | Inventory | Products, catalog, pricing, stock levels, transfers. |
| Hospital & Locations API | Hospital | Organizations, locations, providers, rooms. |
| Lab & Diagnostics API | Lab | Diagnostic lab orders and results. |
| Reminders API | Reminders | Due/overdue service reminders and recalls. |
| Conversations & Communications API | Conversations / Marketing | Client messaging threads, templates, campaigns. |
| Analytics & Reporting API | Analytics | Aggregate practice metrics and reporting datasets. |
| Events API | Events | Queryable log of platform events for auditing and sync. |

## GraphQL

- [GraphQL Overview](graphql/vetspire-graphql.md)
- [GraphQL Schema (modeled SDL)](graphql/vetspire-schema.graphql)

Production endpoint `https://api.vetspire.com/graphql`; staging `https://api.staging.vetspire.com/graphql`; sandbox `https://api.sandbox.vetspire.com/graphql`. Authenticate with an API token in the `Authorization` header. Maximum query depth is 8.

> The schema SDL in this repository is a **representative, modeled** surface grounded in the documented domains at [developer.vetspire.com](https://developer.vetspire.com/). The full production schema is only introspectable with a valid API token; confirm exact field names against the developer reference and live introspection.

## Collections

- [Postman Collection](collections/vetspire.postman_collection.json)
- [Open Collection](collections/vetspire.opencollection.json)

## Common Properties

- [GitHub Organization](https://github.com/vetspire)
- [LinkedIn](https://www.linkedin.com/company/vetspire)
- [Website](https://vetspire.com/)
- [Documentation](https://developer.vetspire.com/)
- [Plans](plans/vetspire-plans-pricing.yml)
- [Rate Limits](rate-limits/vetspire-rate-limits.yml)
- [Fin Ops](finops/vetspire-finops.yml)
- [Support](https://support.vetspire.com/support/solutions/folders/70000486207)

## Pricing

Vetspire is a per-practice SaaS billed per full-time veterinarian (DVM) per month (Standard ~$299, Pro ~$379; Enterprise volume pricing ~$249-$329 for large multi-location groups). The GraphQL API is included with a subscription and is **not** separately metered or billed. See [Plans](plans/vetspire-plans-pricing.yml).

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
