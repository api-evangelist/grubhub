# Grubhub (grubhub)
Grubhub is an online food ordering and delivery marketplace connecting diners with local restaurants. Their developer platform provides APIs for POS integrations and delivery partners to manage menus, orders, merchant data, scheduling, deliveries, and merchant onboarding across the Grubhub network.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/grubhub/refs/heads/main/apis.yml)

## Scope

- **Type:** Contract
- **Position:** Consuming
- **Access:** 3rd-Party

## Tags:

 - Food Delivery, Online Ordering, Restaurants, Logistics, Merchants

## Timestamps

- **Created:** 2026-03-20
- **Modified:** 2026-03-20

## APIs

### Grubhub Menu API
The Grubhub Menu API enables partners and merchants to create, update, and manage restaurant menus within the Grubhub Marketplace. It supports building normalized menu structures including categories, items, modifiers, and pricing. POS integrations are required to sync menus through this API, ensuring that restaurant offerings on Grubhub stay current with their local menu changes.

**Human URL:** [https://developer.grubhub.com/api/menu](https://developer.grubhub.com/api/menu)


#### Tags:

 - Food Delivery, Menus, Restaurants, Online Ordering

#### Properties

- [Documentation](https://developer.grubhub.com/api/menu)
- [OpenAPI](openapi/grubhub-menu-openapi.yml)

### Grubhub Orders API
The Grubhub Orders API allows partners to receive, manage, and update order statuses for restaurant orders placed through the Grubhub Marketplace. When a customer places an order, Grubhub sends it to the partner's endpoint via webhook subscription. Partners can confirm orders, update preparation status, mark orders as ready for pickup, and track delivery progress through defined order lifecycle states.

**Human URL:** [https://developer.grubhub.com/api/orders](https://developer.grubhub.com/api/orders)


#### Tags:

 - Food Delivery, Orders, Restaurants, Online Ordering, Webhooks

#### Properties

- [Documentation](https://developer.grubhub.com/api/orders)
- [OpenAPI](openapi/grubhub-orders-openapi.yml)
- [AsyncAPI](asyncapi/grubhub-order-events-asyncapi.yml)

### Grubhub Merchant Data API
The Grubhub Merchant Data API provides endpoints for managing merchant information, including store details, tax rates, fulfillment settings, and configuration groups. Partners can retrieve all Grubhub locations associated with a merchant's account, update merchant profiles, and manage operational settings. This API is essential for maintaining accurate restaurant data across the Grubhub platform.

**Human URL:** [https://developer.grubhub.com/api/merchant-data](https://developer.grubhub.com/api/merchant-data)


#### Tags:

 - Food Delivery, Merchants, Restaurants, Data Management

#### Properties

- [Documentation](https://developer.grubhub.com/api/merchant-data)
- [OpenAPI](openapi/grubhub-merchant-data-openapi.yml)

### Grubhub Merchant Schedules API
The Grubhub Merchant Schedules API allows partners to manage restaurant operating hours and availability on the Grubhub Marketplace. It supports setting regular business hours, temporary closures, and special holiday schedules. Partners can check merchant availability status and update schedules to ensure customers see accurate ordering windows for each restaurant location.

**Human URL:** [https://developer.grubhub.com/docs/6uXmPesMoYmoV6jZx6lVfa/checking-merchant-availability](https://developer.grubhub.com/docs/6uXmPesMoYmoV6jZx6lVfa/checking-merchant-availability)


#### Tags:

 - Food Delivery, Scheduling, Restaurants, Availability

#### Properties

- [Documentation](https://developer.grubhub.com/docs/6uXmPesMoYmoV6jZx6lVfa/checking-merchant-availability)
- [OpenAPI](openapi/grubhub-merchant-schedules-openapi.yml)

### Grubhub Deliveries API
The Grubhub Deliveries API enables partners to manage delivery logistics and interact with Grubhub's nationwide courier network. It provides delivery status tracking through key states including driver assignment, pickup ready, and out for delivery. Partners can leverage Grubhub Connect, a full-service delivery solution for delivery aggregators, marketplaces, and enterprise merchants to fulfill orders using Grubhub drivers.

**Human URL:** [https://developer.grubhub.com/docs/2xRv0wZtNljuMTpizzNqD2/interacting-with-drivers](https://developer.grubhub.com/docs/2xRv0wZtNljuMTpizzNqD2/interacting-with-drivers)


#### Tags:

 - Food Delivery, Logistics, Drivers, Delivery Tracking

#### Properties

- [Documentation](https://developer.grubhub.com/docs/2xRv0wZtNljuMTpizzNqD2/interacting-with-drivers)
- [OpenAPI](openapi/grubhub-deliveries-openapi.yml)
- [AsyncAPI](asyncapi/grubhub-delivery-events-asyncapi.yml)

### Grubhub Onboarding API
The Grubhub Onboarding API enables partners to offer self-service integration onboarding directly to their merchants using OAuth-based authentication. It provides endpoints for new merchant referrals, merchant activation and deactivation, merchant association, and reporting onboarding issues. The API can reduce merchant onboarding time from 7-10 days down to as little as 5-10 minutes, significantly decreasing integration downtime.

**Human URL:** [https://developer.grubhub.com/api/onboarding](https://developer.grubhub.com/api/onboarding)


#### Tags:

 - Food Delivery, Onboarding, Merchants, Integration

#### Properties

- [Documentation](https://developer.grubhub.com/api/onboarding)
- [OpenAPI](openapi/grubhub-onboarding-openapi.yml)

## Common Properties

- [Developer Portal](https://developer.grubhub.com/)
- [Website](https://www.grubhub.com/)
- [PrivacyPolicy](https://www.grubhub.com/legal/privacy-policy)
- [TermsOfService](https://www.grubhub.com/legal/terms-of-use)
- [Support](https://www.grubhub.com/help/contact-us)
- [Blog](https://about.grubhub.com/news/)
- [Login](https://developer.grubhub.com/login)

## Maintainers

**FN:** API Evangelist

**Email:** info@apievangelist.com
