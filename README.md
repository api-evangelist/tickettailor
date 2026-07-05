# Ticket Tailor (tickettailor)

Ticket Tailor is an online event ticketing platform that lets organizers sell tickets and manage box offices for events, from single dates to recurring event series. Its public REST API (base `https://api.tickettailor.com/v1`) exposes the box office programmatically - events, event series, orders, issued tickets, ticket types, ticket groups, vouchers, and check-ins - using conventional HTTP methods (GET, POST, PUT, PATCH, DELETE). The API is read-and-write, supports cursor-based pagination, and is rate limited to 5000 requests per 30 minutes.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/tickettailor/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/tickettailor/refs/heads/main/apis.yml)

## Access Model

The Ticket Tailor API is public and self-serve. Any account holder can generate an API key in their box office settings and start calling the API immediately - there is no partner-only gate or approval process. Each API key is scoped to the box office that issued it and can only access that box office's data.

**Authentication is API key over HTTP Basic Auth:** supply your API key as the username and leave the password blank (`Authorization: Basic base64(apiKey:)`). Keys are managed under box office settings.

There is no separate charge for API access. Ticket Tailor's cost is a low per-ticket fee on paid tickets (free events and the first five sales are free); the same account and pricing apply whether you sell through the hosted box office or via the API. See [plans/tickettailor-plans-pricing.yml](plans/tickettailor-plans-pricing.yml).

## Tags

- Event Ticketing
- Events
- Ticketing
- Box Office
- Payments
- Registration

## Timestamps

- **Created:** 2026-07-05
- **Modified:** 2026-07-05

## APIs

### Ticket Tailor Events API

List and retrieve the individual event dates in a box office. Each event is a scheduled occurrence (with its own ticket sales) that belongs to an event series. Supports cursor-based pagination and filtering.

- **Human URL:** [https://developers.tickettailor.com/docs/api/get-all-events](https://developers.tickettailor.com/docs/api/get-all-events)
- **Base URL:** `https://api.tickettailor.com/v1`

#### Tags

- Events
- Box Office

#### Properties

- [Documentation](https://developers.tickettailor.com/docs/intro/)
- [API Reference](https://developers.tickettailor.com/docs/api/get-all-events)
- [OpenAPI](openapi/tickettailor-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/tickettailor.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/tickettailor.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Ticket Tailor Event Series API

Create, list, retrieve, update, delete, and change the status of event series - the parent container that groups one or more event dates. Also creates ticket types and ticket groups scoped to a series.

- **Human URL:** [https://developers.tickettailor.com/docs/api/get-all-event-series](https://developers.tickettailor.com/docs/api/get-all-event-series)
- **Base URL:** `https://api.tickettailor.com/v1`

#### Tags

- Event Series
- Ticket Types
- Recurring

#### Properties

- [API Reference](https://developers.tickettailor.com/docs/api/get-all-event-series)
- [OpenAPI](openapi/tickettailor-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/tickettailor.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/tickettailor.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Ticket Tailor Orders API

List, retrieve, and update orders belonging to a box office. An order captures the buyer, line items, payment, and the issued tickets produced by a purchase.

- **Human URL:** [https://developers.tickettailor.com/docs/api/get-all-orders](https://developers.tickettailor.com/docs/api/get-all-orders)
- **Base URL:** `https://api.tickettailor.com/v1`

#### Tags

- Orders
- Sales
- Buyers

#### Properties

- [API Reference](https://developers.tickettailor.com/docs/api/get-all-orders)
- [OpenAPI](openapi/tickettailor-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/tickettailor.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/tickettailor.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Ticket Tailor Issued Tickets API

List, retrieve, create, and void the individual tickets issued to attendees. Each issued ticket carries the holder's details, barcode, and check-in state and is linked to an order and an event.

- **Human URL:** [https://developers.tickettailor.com/docs/api/get-all-issued-tickets](https://developers.tickettailor.com/docs/api/get-all-issued-tickets)
- **Base URL:** `https://api.tickettailor.com/v1`

#### Tags

- Issued Tickets
- Attendees
- Void

#### Properties

- [API Reference](https://developers.tickettailor.com/docs/api/get-all-issued-tickets)
- [OpenAPI](openapi/tickettailor-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/tickettailor.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/tickettailor.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Ticket Tailor Vouchers API

Create, list, retrieve, modify, and delete vouchers and inspect their redeemable voucher codes. Vouchers grant buyers discounted or comped access at checkout.

- **Human URL:** [https://developers.tickettailor.com/docs/api/get-voucher-list](https://developers.tickettailor.com/docs/api/get-voucher-list)
- **Base URL:** `https://api.tickettailor.com/v1`

#### Tags

- Vouchers
- Discounts
- Codes

#### Properties

- [API Reference](https://developers.tickettailor.com/docs/api/get-voucher-list)
- [OpenAPI](openapi/tickettailor-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/tickettailor.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/tickettailor.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Ticket Tailor Check-ins API

List and record check-ins as attendees arrive at the door. Check-ins mark issued tickets as scanned/admitted for on-site entry management.

- **Human URL:** [https://developers.tickettailor.com/docs/api/get-check-in-list](https://developers.tickettailor.com/docs/api/get-check-in-list)
- **Base URL:** `https://api.tickettailor.com/v1`

#### Tags

- Check-ins
- Scanning
- Entry

#### Properties

- [API Reference](https://developers.tickettailor.com/docs/api/get-check-in-list)
- [OpenAPI](openapi/tickettailor-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/tickettailor.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/tickettailor.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/ticket-tailor)
- [Website](https://www.tickettailor.com)
- [Documentation](https://developers.tickettailor.com/docs/intro/)
- [Plans](plans/tickettailor-plans-pricing.yml)
- [Rate Limits](rate-limits/tickettailor-rate-limits.yml)
- [Fin Ops](finops/tickettailor-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
