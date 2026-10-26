# Ticket Tailor (tickettailor)

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
