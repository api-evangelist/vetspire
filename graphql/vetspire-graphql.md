# Vetspire GraphQL API

Vetspire is a cloud-based veterinary practice management platform. Its entire public API is GraphQL - "every action within Vetspire is powered by GraphQL requests." Clients declare exactly the fields they need across veterinary practice domains (Accounts, Clinical, Schedule, Billing, Inventory, Hospital, Lab, Reminders, Conversations, Analytics, Events).

**Endpoint (production):** `https://api.vetspire.com/graphql`
**Endpoint (staging):** `https://api.staging.vetspire.com/graphql`
**Endpoint (sandbox):** `https://api.sandbox.vetspire.com/graphql`

**Authentication:** Every request must include an API token in the `Authorization` HTTP header over HTTPS. Tokens are provisioned by a Vetspire administrator and should be treated as sensitive credentials.

**Transport:** All operations are HTTP `POST` to the single `/graphql` endpoint with a JSON body containing `query` and optional `variables`.

**Query depth limit:** Vetspire enforces a maximum query depth of 8. Exceeding it returns error code `query_depth_limit` ("Query has depth of 9, which exceeds max depth of 8").

## Documentation

- Interactive schema reference: https://developer.vetspire.com/
- API overview: https://support.vetspire.com/support/solutions/articles/70000636887-vetspire-s-api-overview
- GraphQL & Vetspire: https://support.vetspire.com/support/solutions/articles/70000670311-graphql-vetspire
- Hasura Cloud explorer guide: https://support.vetspire.com/support/solutions/articles/70000669182-accessing-and-using-hasura-cloud-for-vetspire-graphql-exploration
- API Query Library: https://support.vetspire.com/support/solutions/articles/70000672851-vetspire-api-query-library

## Schema coverage (per developer.vetspire.com)

- **Query domains (24):** Accounts, Analytics, Billing, Board, Boarding, Clinical, Conversations, Entities, Events, Hospital, Inventory, Lab, Marketing, Notifications, Plan, RDVMS, Reminders, Schedule, Tasks, Telemedicine, Treatment, Triggers, Voice Call, New Billing.
- **Mutation domains (26):** all query domains plus Comments, License, and Payroll.
- **Type system:** 400+ object types, 5 unions, 248 input objects, 112 enums.

## Example query (Searching Accounts / Clients)

```graphql
query SearchClients($searchTerm: String!) {
  clients(searchTerm: $searchTerm) {
    id
    givenName
    familyName
    email
    phoneNumber
    balance
    patients {
      id
      name
      species
      breed
    }
  }
}
```

## Example query (Appointments for a location)

```graphql
query LocationAppointments($locationId: ID!, $start: DateTime!, $end: DateTime!) {
  appointments(locationId: $locationId, start: $start, end: $end) {
    id
    start
    end
    type
    status
    patient { id name }
    client { id givenName familyName }
    provider { id name }
  }
}
```

## Notes

- The companion `vetspire-schema.graphql` in this repository is a **representative, modeled** SDL covering the documented domains and the operations most commonly used (clients, patients, appointments, encounters, invoices, products, locations, reminders, lab, conversations, analytics, events). The full production schema is only introspectable with a valid API token; exact field names and the complete 400+ type surface should be confirmed against https://developer.vetspire.com/ and live introspection.
- Schema home: https://github.com/api-evangelist/vetspire
