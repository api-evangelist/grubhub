# grubhub (grubhub)

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
