---
name: grubhub-connect-delivery
description: Quote, dispatch, track, amend and cancel a last-mile delivery on Grubhub's courier network (Grubhub Connect / DaaS), including the test path.
api: Grubhub Connect (Delivery as a Service)
generated: '2026-09-17'
method: generated
source: openapi/grubhub-connect-endpoints-openapi.yml, openapi/grubhub-connect-webhooks-openapi.yml
base_url: https://api-third-party-gtm.grubhub.com
operations:
  - getServiceAreas
  - requestDeliveryQuote
  - acceptDeliveryQuote
  - getStatus
  - createProxyPhoneNumber
  - updateDeliveryDropoffLocation
  - updatePickupVerification
  - pickupReady
  - updateCourierTip
  - cancelDelivery
  - requestRefund
  - progressDelivery
  - progressRefund
  - emulateStatusUpdateWebhook
  - emulateRefundUpdateWebhook
---

# Run a delivery on Grubhub Connect

Every operation takes `X-GH-PARTNER-KEY`. Every operation can return `403` ("Request Forbidden") when
the partner key does not cover that delivery.

## Steps

1. **Check coverage.** `GET /delivery/daas/v1/servicearea` (`getServiceAreas`).
2. **Quote.** `POST /delivery/daas/v1/quote` (`requestDeliveryQuote`). Set the boolean header
   `x-gh-daas-test: true` to make this a test delivery — it works in production too, and the
   resulting delivery can then only be progressed by the test endpoints.
3. **Accept.** `POST /delivery/daas/v1/quote/{quoteId}/accept` (`acceptDeliveryQuote`). A `400`
   "Delivery quote expired" means requote — the contract does not publish how long a quote lives.
4. **Signal readiness.** `POST /delivery/daas/v1/{deliveryId}/pickupReady` (`pickupReady`).
5. **Track.** `GET /delivery/daas/v1/{deliveryId}` (`getStatus`), and subscribe to the
   `[Egress] Delivery Status Update Webhook`. The event types are real schemas: `Created`,
   `Assigned`, `Unassigned`, `CourierAtPickup`, `PickedUp`, `InTransit`, `CourierAtDropoff`,
   `Delivered`, `Canceled`, `ReturnInitiated`, `ReturnCompleted`.
6. **Amend in flight.** `updateDeliveryDropoffLocation`, `updatePickupVerification`,
   `createProxyPhoneNumber` (a masked number for diner-courier contact), `updateCourierTip`.

## Undoing things

- `POST /delivery/daas/v1/{deliveryId}/cancel` (`cancelDelivery`) cancels a delivery.
- `POST /delivery/daas/v1/{deliveryId}/refund` (`requestRefund`) returns `202` and reports back on
  the `[Egress] Delivery Refund Update Webhook`.
- **No window is published for either.** Do not assume one. Check `getStatus` first.
- `updateCourierTip` is an **increase** — there is no decrease and no void.

## Testing

`progressDelivery` and `progressRefund` drive a test delivery through its state machine on demand,
and `emulateStatusUpdateWebhook` / `emulateRefundUpdateWebhook` fire real webhook payloads at your
endpoint. Use these instead of waiting on a courier.
