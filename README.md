# Vetspire (vetspire)

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
