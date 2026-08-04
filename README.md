# grubhub (grubhub)

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

Grubhub works with brands, point of sale companies, and online ordering providers to power an ordering experience in Grubhub Marketplace and within restaurant-branded web experiences. This documentation describes the normalized endpoints required for ingesting menu content and facilitating order transmission.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/grubhub/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/grubhub/refs/heads/main/apis.yml)

## Timestamps

- **Modified:** 2026-05-19

## APIs

### Grubhub Menu API

The Grubhub Menu API enables partners and merchants to create, update, and manage restaurant menus within the Grubhub Marketplace. It supports building normalized menu structures including categories, items, modifiers, and pricing. POS integrations are required to sync menus through this API, ensuring that restaurant offerings on Grubhub stay current with their local menu changes.

- **Human URL:** [https://developer.grubhub.com/api/menu](https://developer.grubhub.com/api/menu)
- **Base URL:** `https://api.grubhub.com`

#### Tags

- Food Delivery
- Menus
- Online Ordering
- Restaurants

#### Properties

- [Documentation](https://developer.grubhub.com/api/menu)
- [OpenAPI](openapi/grubhub-menu-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/grubhub-menu.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/grubhub-menu.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Grubhub Orders API

The Grubhub Orders API allows partners to receive, manage, and update order statuses for restaurant orders placed through the Grubhub Marketplace. When a customer places an order, Grubhub sends it to the partner's endpoint via webhook subscription. Partners can confirm orders, update preparation status, mark orders as ready for pickup, and track delivery progress through defined order lifecycle states.

- **Human URL:** [https://developer.grubhub.com/api/orders](https://developer.grubhub.com/api/orders)
- **Base URL:** `https://api.grubhub.com`

#### Tags

- Food Delivery
- Online Ordering
- Orders
- Restaurants
- Webhooks

#### Properties

- [Documentation](https://developer.grubhub.com/api/orders)
- [OpenAPI](openapi/grubhub-orders-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/grubhub-orders.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/grubhub-orders.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [AsyncAPI](asyncapi/grubhub-order-events-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)

### Grubhub Merchant Data API

The Grubhub Merchant Data API provides endpoints for managing merchant information, including store details, tax rates, fulfillment settings, and configuration groups. Partners can retrieve all Grubhub locations associated with a merchant's account, update merchant profiles, and manage operational settings. This API is essential for maintaining accurate restaurant data across the Grubhub platform.

- **Human URL:** [https://developer.grubhub.com/api/merchant-data](https://developer.grubhub.com/api/merchant-data)
- **Base URL:** `https://api.grubhub.com`

#### Tags

- Data Management
- Food Delivery
- Merchants
- Restaurants

#### Properties

- [Documentation](https://developer.grubhub.com/api/merchant-data)
- [OpenAPI](openapi/grubhub-merchant-data-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/grubhub-merchant-data.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/grubhub-merchant-data.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Grubhub Merchant Schedules API

The Grubhub Merchant Schedules API allows partners to manage restaurant operating hours and availability on the Grubhub Marketplace. It supports setting regular business hours, temporary closures, and special holiday schedules. Partners can check merchant availability status and update schedules to ensure customers see accurate ordering windows for each restaurant location.

- **Human URL:** [https://developer.grubhub.com/docs/6uXmPesMoYmoV6jZx6lVfa/checking-merchant-availability](https://developer.grubhub.com/docs/6uXmPesMoYmoV6jZx6lVfa/checking-merchant-availability)
- **Base URL:** `https://api.grubhub.com`

#### Tags

- Availability
- Food Delivery
- Restaurants
- Scheduling

#### Properties

- [Documentation](https://developer.grubhub.com/docs/6uXmPesMoYmoV6jZx6lVfa/checking-merchant-availability)
- [OpenAPI](openapi/grubhub-merchant-schedules-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/grubhub-merchant-schedules.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/grubhub-merchant-schedules.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Grubhub Deliveries API

The Grubhub Deliveries API enables partners to manage delivery logistics and interact with Grubhub's nationwide courier network. It provides delivery status tracking through key states including driver assignment, pickup ready, and out for delivery. Partners can leverage Grubhub Connect, a full-service delivery solution for delivery aggregators, marketplaces, and enterprise merchants to fulfill orders using Grubhub drivers.

- **Human URL:** [https://developer.grubhub.com/docs/2xRv0wZtNljuMTpizzNqD2/interacting-with-drivers](https://developer.grubhub.com/docs/2xRv0wZtNljuMTpizzNqD2/interacting-with-drivers)
- **Base URL:** `https://api.grubhub.com`

#### Tags

- Delivery Tracking
- Drivers
- Food Delivery
- Logistics

#### Properties

- [Documentation](https://developer.grubhub.com/docs/2xRv0wZtNljuMTpizzNqD2/interacting-with-drivers)
- [OpenAPI](openapi/grubhub-deliveries-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/grubhub-deliveries.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/grubhub-deliveries.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [AsyncAPI](asyncapi/grubhub-delivery-events-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)

### Grubhub Onboarding API

The Grubhub Onboarding API enables partners to offer self-service integration onboarding directly to their merchants using OAuth-based authentication. It provides endpoints for new merchant referrals, merchant activation and deactivation, merchant association, and reporting onboarding issues. The API can reduce merchant onboarding time from 7-10 days down to as little as 5-10 minutes, significantly decreasing integration downtime.

- **Human URL:** [https://developer.grubhub.com/api/onboarding](https://developer.grubhub.com/api/onboarding)
- **Base URL:** `https://api.grubhub.com`

#### Tags

- Food Delivery
- Integration
- Merchants
- Onboarding

#### Properties

- [Documentation](https://developer.grubhub.com/api/onboarding)
- [OpenAPI](openapi/grubhub-onboarding-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/grubhub-onboarding.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/grubhub-onboarding.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/GrubhubProd)
- [LinkedIn](https://www.linkedin.com/company/grubhub-seamless)
- [JSON-LD](json-ld/grubhub-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [JSON Schema](json-schema/grubhub-order-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/grubhub-menu-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/grubhub-merchant-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Vocabulary](vocabulary/grubhub-vocabulary.yml)
- [Rules](rules/grubhub-spectral-rules.yml)
- [Plans](plans/grubhub-plans-pricing.yml)
- [Rate Limits](rate-limits/grubhub-rate-limits.yml)
- [Fin Ops](finops/grubhub-finops.yml)
