---
name: grubhub-order-fulfillment
description: Receive a Grubhub Marketplace order, move it through its status lifecycle, request a change, and add pickup instructions.
api: Grubhub Orders API
generated: '2026-09-17'
method: generated
source: openapi/grubhub-orders-openapi.yml
base_url: https://api-third-party-gtm.grubhub.com
operations:
  - getPosOrdersByMerchantStatusDateRange
  - getPosOrdersByGroupStatusDateRange
  - getPosOrderByOrderUuid
  - updateExternalOrderStatusByOrderUuid
  - changeExternalOrder
  - getChangeRequests
  - addPickupInstructionsToOrder
---

# Fulfill a Grubhub Marketplace order

New orders arrive by **webhook**. Grubhub configures the webhook URL by hand during partner
onboarding — there is no API to set or change it. Polling exists as a fallback, not as the design.

## Steps

1. **Receive.** Take the order UUID from the webhook payload, or fall back to
   `GET /pos/v1/merchant/{merchant_long_id}/orders` (`getPosOrdersByMerchantStatusDateRange`) with
   `status`, `start` and `end`. For a multi-location brand use
   `GET /pos/v1/group/{group_key}/orders` (`getPosOrdersByGroupStatusDateRange`).
2. **Read the order.** `GET /pos/v1/merchant/{merchant_long_id}/orders/{order_uuid}`
   (`getPosOrderByOrderUuid`) returns a `PosOrder`.
3. **Advance the status.** `PUT /pos/v1/merchant/{merchant_long_id}/orders/{order_uuid}/status`
   (`updateExternalOrderStatusByOrderUuid`).
4. **Change an order if the kitchen cannot fulfil it as placed.**
   `POST /pos/v1/merchant/{merchant_long_id}/orders/{order_uuid}/changerequests`
   (`changeExternalOrder`), then poll
   `GET .../changerequests` (`getChangeRequests`) for the `OrderChangeRequestStatus`.
5. **Pickup orders.** `POST /pos/v1/merchant/{merchant_id}/orders/{order_uuid}/addpickupinstructions`
   (`addPickupInstructionsToOrder`) returns `204`.

## Rules

- **A status transition is irreversible.** No operation reverts it. Read the order back before
  writing a status you are unsure about.
- **There is no idempotency key.** A retried `PUT .../status` is a second write.
- Note the identifier switch inside this one API: steps 1–4 take `merchant_long_id`; step 5 takes
  `merchant_id`. This is what the contract says, and both are untyped strings.
- The only rate-limit signal in the whole Grubhub contract is a `429` on the Deliveries read. Assume
  a budget exists, batch reads, and prefer the webhook over polling.
