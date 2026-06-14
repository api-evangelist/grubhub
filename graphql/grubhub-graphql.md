# Grubhub GraphQL Schema

This document describes a conceptual GraphQL schema for the Grubhub food delivery marketplace platform. Grubhub provides REST APIs for partners and merchants to manage menus, orders, deliveries, merchant data, scheduling, and onboarding. This GraphQL schema represents the same domain model in a unified, type-safe graph, enabling richer queries across the Grubhub data model.

## Overview

Grubhub operates as a two-sided marketplace connecting customers to restaurants. The platform exposes APIs to POS integrators, delivery aggregators, and enterprise merchants. This schema covers:

- Restaurant and menu management (menus, sections, items, modifiers, pricing)
- Order lifecycle (cart, checkout, order, tracking, fulfillment)
- Delivery logistics (drivers, location, proof of delivery)
- Merchant operations (hours, availability, schedules, service areas)
- Customer-facing features (reviews, ratings, loyalty, promotions)
- Payment and financial operations (payment methods, gift cards, corporate orders)
- Platform integration (API keys, tokens, webhooks)

## Schema Source

Derived from the Grubhub developer documentation at https://developer.grubhub.com/ covering the Menu API, Orders API, Merchant Data API, Merchant Schedules API, Deliveries API, and Onboarding API.

## Root Types

### Query

- `restaurant(id: ID!): Restaurant` — Fetch a single restaurant by ID.
- `restaurants(cuisineType: String, location: String, page: Int, pageSize: Int): [Restaurant]` — List restaurants with optional filters.
- `menu(restaurantId: ID!): RestaurantMenu` — Get the full menu for a restaurant.
- `menuItem(itemId: ID!): MenuItemDetails` — Get details for a specific menu item.
- `order(orderId: ID!): Order` — Retrieve a specific order.
- `orderHistory(customerId: ID!, page: Int, pageSize: Int): [OrderHistory]` — List past orders for a customer.
- `cart(cartId: ID!): Cart` — Retrieve an active cart.
- `delivery(deliveryId: ID!): Delivery` — Get delivery status and details.
- `customer(customerId: ID!): Customer` — Fetch a customer profile.
- `promotion(promoCode: String!): Promotion` — Look up a promotion by code.
- `loyaltyProgram(customerId: ID!): LoyaltyProgram` — Get loyalty status for a customer.
- `serviceArea(restaurantId: ID!): ServiceArea` — Get delivery service area for a restaurant.

### Mutation

- `addItemToCart(cartId: ID!, item: CartItemInput!): Cart` — Add an item to a cart.
- `removeItemFromCart(cartId: ID!, cartItemId: ID!): Cart` — Remove an item from a cart.
- `applyPromoCode(cartId: ID!, code: String!): Cart` — Apply a promo code to a cart.
- `checkout(cartId: ID!, paymentMethodId: ID!): Order` — Convert a cart into a placed order.
- `cancelOrder(orderId: ID!, reason: String): Order` — Cancel a placed order.
- `confirmOrder(orderId: ID!): Order` — Confirm receipt of an order (merchant side).
- `updateOrderStatus(orderId: ID!, status: OrderStatusEnum!): Order` — Advance order through lifecycle states.
- `submitReview(review: ReviewInput!): Review` — Submit a customer review for an order.
- `addPaymentMethod(customerId: ID!, method: PaymentMethodInput!): PaymentMethod` — Add a payment method to a customer account.
- `redeemGiftCard(customerId: ID!, giftCardCode: String!): GiftCard` — Redeem a gift card balance.
- `registerWebhook(endpoint: String!, events: [String!]!): Webhook` — Register a webhook endpoint.

### Subscription

- `orderStatusUpdated(orderId: ID!): OrderTracking` — Stream real-time order status changes.
- `driverLocationUpdated(deliveryId: ID!): DriverLocation` — Stream driver GPS position updates.

## Core Types

### Restaurant

The central entity representing a restaurant location on the Grubhub marketplace. Maps to merchant data managed via the Merchant Data API.

Fields include restaurant ID, name, description, cuisine types, address, contact details, rating, review count, photos, operating hours, delivery details, and service area configuration.

### Menu and Items

`RestaurantMenu` aggregates all `Menu` objects for a restaurant. A `Menu` contains `MenuSection` objects (categories), each holding `MenuItem` entries. Items carry `MenuItemDetails` with full descriptions, dietary flags, allergen data, nutrition information, and customization groups.

### Order Lifecycle

`Cart` captures items before checkout. `Checkout` handles payment and address validation. `Order` represents a placed order with a full lifecycle tracked through `OrderStatus` and `OrderTracking`. `OrderHistory` provides paginated past orders.

### Delivery

`Delivery` links an order to a courier. `DeliveryDriver` carries driver identity and contact info. `DriverLocation` provides live GPS coordinates. `DeliveryProof` stores photo or signature confirmation of handoff.

### Promotions and Loyalty

`Promotion` and `PartnerPromotion` cover discount codes and merchant-funded offers. `PromoCode` captures redemption details. `LoyaltyProgram` and `GrubhubPerks` model the customer rewards system.

### Customer and Payments

`Customer` holds profile and preference data. `CustomerAddress` and `SavedAddress` manage delivery destinations. `PaymentMethod` covers cards and digital wallets. `GiftCard` tracks balance. `CorporateOrder` handles business ordering accounts.

### Platform Integration

`APIKey` and `Token` manage authentication credentials. `Webhook` defines event subscriptions for order and delivery events.

## Enumerations

- `OrderStatusEnum`: PLACED, CONFIRMED, PREPARING, READY_FOR_PICKUP, OUT_FOR_DELIVERY, DELIVERED, CANCELLED, REFUNDED
- `DietaryEnum`: VEGETARIAN, VEGAN, GLUTEN_FREE, HALAL, KOSHER, NUT_FREE, DAIRY_FREE
- `AllergenEnum`: PEANUTS, TREE_NUTS, MILK, EGGS, WHEAT, SOYBEAN, FISH, SHELLFISH, SESAME
- `DeliveryStatusEnum`: PENDING, DRIVER_ASSIGNED, PICKED_UP, OUT_FOR_DELIVERY, DELIVERED, FAILED
- `PaymentMethodTypeEnum`: CREDIT_CARD, DEBIT_CARD, PAYPAL, APPLE_PAY, GOOGLE_PAY, GIFT_CARD, CORPORATE_ACCOUNT

## Usage Notes

This schema is conceptual and models the Grubhub partner API surface as a GraphQL graph. Actual Grubhub APIs are REST-based. This schema can be used to understand the domain model, build middleware translation layers, or design internal BFF (backend-for-frontend) GraphQL gateways that aggregate Grubhub REST API calls.

Partners integrating with Grubhub require OAuth-based credentials obtained through the Onboarding API. All mutations that modify order state must be called with appropriate partner authentication tokens.
