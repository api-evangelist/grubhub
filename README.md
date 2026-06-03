# Grubhub (grubhub)
Grubhub works with brands, point of sale companies, and online ordering providers to power an ordering experience in Grubhub Marketplace and within restaurant-branded web experiences. This documentation describes the normalized endpoints required for ingesting menu content and facilitating order transmission.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/grubhub/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - Food Delivery, Online Ordering, Restaurants, Marketplaces, Merchants, Logistics

## Timestamps

- **Modified:** 2026-05-19

## APIs

### Grubhub Menu API
The Grubhub Menu API enables partners and merchants to create, update, and manage restaurant menus within the Grubhub Marketplace. It supports building normalized menu structures including categories, items, modifiers, and pricing. POS integrations are required to sync menus through this API, ensuring that restaurant offerings on Grubhub stay current with their local menu changes.

**Human URL:** [https://developer.grubhub.com/api/menu](https://developer.grubhub.com/api/menu)

#### Tags:

 - Food Delivery, Menus, Online Ordering, Restaurants

#### Properties

- [Documentation](https://developer.grubhub.com/api/menu)
- [OpenAPI](openapi/grubhub-menu-openapi.yml)
- [NaftikoCapability](capabilities/menu-menu-ingestion.yaml)
- [NaftikoCapability](capabilities/menu-menu-retrieval.yaml)
- [NaftikoCapability](capabilities/menu-menu-schedule-overrides.yaml)

### Grubhub Orders API
The Grubhub Orders API allows partners to receive, manage, and update order statuses for restaurant orders placed through the Grubhub Marketplace. When a customer places an order, Grubhub sends it to the partner's endpoint via webhook subscription. Partners can confirm orders, update preparation status, mark orders as ready for pickup, and track delivery progress through defined order lifecycle states.

**Human URL:** [https://developer.grubhub.com/api/orders](https://developer.grubhub.com/api/orders)

#### Tags:

 - Food Delivery, Online Ordering, Orders, Restaurants, Webhooks

#### Properties

- [Documentation](https://developer.grubhub.com/api/orders)
- [OpenAPI](openapi/grubhub-orders-openapi.yml)
- [AsyncAPI](asyncapi/grubhub-order-events-asyncapi.yml)
- [NaftikoCapability](capabilities/orders-order-change-requests.yaml)
- [NaftikoCapability](capabilities/orders-order-polling.yaml)
- [NaftikoCapability](capabilities/orders-order-status.yaml)
- [NaftikoCapability](capabilities/orders-orders.yaml)

### Grubhub Merchant Data API
The Grubhub Merchant Data API provides endpoints for managing merchant information, including store details, tax rates, fulfillment settings, and configuration groups. Partners can retrieve all Grubhub locations associated with a merchant's account, update merchant profiles, and manage operational settings. This API is essential for maintaining accurate restaurant data across the Grubhub platform.

**Human URL:** [https://developer.grubhub.com/api/merchant-data](https://developer.grubhub.com/api/merchant-data)

#### Tags:

 - Data Management, Food Delivery, Merchants, Restaurants

#### Properties

- [Documentation](https://developer.grubhub.com/api/merchant-data)
- [OpenAPI](openapi/grubhub-merchant-data-openapi.yml)
- [NaftikoCapability](capabilities/merchant-data-merchant-properties.yaml)
- [NaftikoCapability](capabilities/merchant-data-merchant-status.yaml)
- [NaftikoCapability](capabilities/merchant-data-merchants.yaml)

### Grubhub Merchant Schedules API
The Grubhub Merchant Schedules API allows partners to manage restaurant operating hours and availability on the Grubhub Marketplace. It supports setting regular business hours, temporary closures, and special holiday schedules. Partners can check merchant availability status and update schedules to ensure customers see accurate ordering windows for each restaurant location.

**Human URL:** [https://developer.grubhub.com/docs/6uXmPesMoYmoV6jZx6lVfa/checking-merchant-availability](https://developer.grubhub.com/docs/6uXmPesMoYmoV6jZx6lVfa/checking-merchant-availability)

#### Tags:

 - Availability, Food Delivery, Restaurants, Scheduling

#### Properties

- [Documentation](https://developer.grubhub.com/docs/6uXmPesMoYmoV6jZx6lVfa/checking-merchant-availability)
- [OpenAPI](openapi/grubhub-merchant-schedules-openapi.yml)
- [NaftikoCapability](capabilities/merchant-schedules-schedule-overrides.yaml)
- [NaftikoCapability](capabilities/merchant-schedules-schedules.yaml)

### Grubhub Deliveries API
The Grubhub Deliveries API enables partners to manage delivery logistics and interact with Grubhub's nationwide courier network. It provides delivery status tracking through key states including driver assignment, pickup ready, and out for delivery. Partners can leverage Grubhub Connect, a full-service delivery solution for delivery aggregators, marketplaces, and enterprise merchants to fulfill orders using Grubhub drivers.

**Human URL:** [https://developer.grubhub.com/docs/2xRv0wZtNljuMTpizzNqD2/interacting-with-drivers](https://developer.grubhub.com/docs/2xRv0wZtNljuMTpizzNqD2/interacting-with-drivers)

#### Tags:

 - Delivery Tracking, Drivers, Food Delivery, Logistics

#### Properties

- [Documentation](https://developer.grubhub.com/docs/2xRv0wZtNljuMTpizzNqD2/interacting-with-drivers)
- [OpenAPI](openapi/grubhub-deliveries-openapi.yml)
- [AsyncAPI](asyncapi/grubhub-delivery-events-asyncapi.yml)
- [NaftikoCapability](capabilities/deliveries-delivery-status.yaml)
- [NaftikoCapability](capabilities/deliveries-driver-communication.yaml)

### Grubhub Onboarding API
The Grubhub Onboarding API enables partners to offer self-service integration onboarding directly to their merchants using OAuth-based authentication. It provides endpoints for new merchant referrals, merchant activation and deactivation, merchant association, and reporting onboarding issues. The API can reduce merchant onboarding time from 7-10 days down to as little as 5-10 minutes, significantly decreasing integration downtime.

**Human URL:** [https://developer.grubhub.com/api/onboarding](https://developer.grubhub.com/api/onboarding)

#### Tags:

 - Food Delivery, Integration, Merchants, Onboarding

#### Properties

- [Documentation](https://developer.grubhub.com/api/onboarding)
- [OpenAPI](openapi/grubhub-onboarding-openapi.yml)
- [NaftikoCapability](capabilities/onboarding-issue-reporting.yaml)
- [NaftikoCapability](capabilities/onboarding-merchant-eligibility.yaml)
- [NaftikoCapability](capabilities/onboarding-merchant-onboarding.yaml)

## Common Properties

- [GitHubOrganization](https://github.com/GrubhubProd)
- [LinkedIn](https://www.linkedin.com/company/grubhub-seamless)
- [JSONLD](json-ld/grubhub-context.jsonld)
- [JSONSchema](json-schema/grubhub-order-schema.json)
- [JSONSchema](json-schema/grubhub-menu-schema.json)
- [JSONSchema](json-schema/grubhub-merchant-schema.json)
- [Vocabulary](vocabulary/grubhub-vocabulary.yml)
- [Rules](rules/grubhub-spectral-rules.yml)
- [Plans](plans/grubhub-plans-pricing.yml)
- [RateLimits](rate-limits/grubhub-rate-limits.yml)
- [FinOps](finops/grubhub-finops.yml)

## Artifacts

Machine-readable API specifications and supporting artifacts organized by format.

### OpenAPI

- [Deliveries OpenAPI](openapi/grubhub-deliveries-openapi.yml)
- [Menu OpenAPI](openapi/grubhub-menu-openapi.yml)
- [Merchant Data OpenAPI](openapi/grubhub-merchant-data-openapi.yml)
- [Merchant Schedules OpenAPI](openapi/grubhub-merchant-schedules-openapi.yml)
- [Onboarding OpenAPI](openapi/grubhub-onboarding-openapi.yml)
- [Orders OpenAPI](openapi/grubhub-orders-openapi.yml)

### AsyncAPI

- [Delivery Events AsyncAPI](asyncapi/grubhub-delivery-events-asyncapi.yml)
- [Order Events AsyncAPI](asyncapi/grubhub-order-events-asyncapi.yml)

### JSON Schema

54 JSON Schema files in [`json-schema/`](json-schema/).

### JSON Structure

54 JSON Structure files in [`json-structure/`](json-structure/).

### Examples

54 Examples files in [`examples/`](examples/).

### JSON-LD

- [Grubhub Context](json-ld/grubhub-context.jsonld)


## Capabilities

Self-contained Naftiko capabilities, one per API business surface, each exposing both a REST and an MCP adapter.

| Capability | API | Tools |
|------------|-----|-------|
| [Grubhub Deliveries API — Delivery Status](capabilities/deliveries-delivery-status.yaml) | Deliveries | 1 |
| [Grubhub Deliveries API — Driver Communication](capabilities/deliveries-driver-communication.yaml) | Deliveries | 1 |
| [Grubhub Menu API — Menu Ingestion](capabilities/menu-menu-ingestion.yaml) | Menu | 2 |
| [Grubhub Menu API — Menu Retrieval](capabilities/menu-menu-retrieval.yaml) | Menu | 1 |
| [Grubhub Menu API — Menu Schedule Overrides](capabilities/menu-menu-schedule-overrides.yaml) | Menu | 2 |
| [Grubhub Merchant Data API — Merchant Properties](capabilities/merchant-data-merchant-properties.yaml) | Merchant Data | 3 |
| [Grubhub Merchant Data API — Merchant Status](capabilities/merchant-data-merchant-status.yaml) | Merchant Data | 2 |
| [Grubhub Merchant Data API — Merchants](capabilities/merchant-data-merchants.yaml) | Merchant Data | 2 |
| [Grubhub Merchant Schedules API — Schedule Overrides](capabilities/merchant-schedules-schedule-overrides.yaml) | Merchant Schedules | 2 |
| [Grubhub Merchant Schedules API — Schedules](capabilities/merchant-schedules-schedules.yaml) | Merchant Schedules | 6 |
| [Grubhub Onboarding API — Issue Reporting](capabilities/onboarding-issue-reporting.yaml) | Onboarding | 1 |
| [Grubhub Onboarding API — Merchant Eligibility](capabilities/onboarding-merchant-eligibility.yaml) | Onboarding | 1 |
| [Grubhub Onboarding API — Merchant Onboarding](capabilities/onboarding-merchant-onboarding.yaml) | Onboarding | 5 |
| [Grubhub Orders API — Order Change Requests](capabilities/orders-order-change-requests.yaml) | Orders | 1 |
| [Grubhub Orders API — Order Polling](capabilities/orders-order-polling.yaml) | Orders | 1 |
| [Grubhub Orders API — Order Status](capabilities/orders-order-status.yaml) | Orders | 2 |
| [Grubhub Orders API — Orders](capabilities/orders-orders.yaml) | Orders | 2 |

## Vocabulary

- [Grubhub Vocabulary](vocabulary/grubhub-vocabulary.yml) — Unified taxonomy mapping 17 resources, 12 actions, 17 workflows, and 3 personas across operational (OpenAPI) and capability (Naftiko) dimensions

## Rules

- [Grubhub Spectral Rules](rules/grubhub-spectral-rules.yml) — 44 rules enforcing Grubhub API conventions (paths, naming, security, responses, examples)

## Commercial

- [Plans & Pricing](plans/grubhub-plans-pricing.yml) — API Commons Plans: partner integration plus tiered Marketplace commission plans
- [Rate Limits](rate-limits/grubhub-rate-limits.yml) — API Commons Rate Limits: ~200-400 requests/minute per source, 429 on exceed
- [FinOps](finops/grubhub-finops.yml) — FOCUS-aligned FinOps: tiered take-rate commercial model

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
