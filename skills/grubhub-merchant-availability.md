---
name: grubhub-merchant-availability
description: Control whether a Grubhub merchant is taking orders — busy intervals, open/close now, schedule overrides, repeating schedules, and batch online/offline status with job polling.
api: Grubhub Merchant Schedules, Busy Intervals and Merchant Data APIs
generated: '2026-09-17'
method: generated
source: openapi/grubhub-merchant-schedules-openapi.yml, openapi/grubhub-busy-intervals-openapi.yml, openapi/grubhub-merchant-data-openapi.yml
base_url: https://api-third-party-gtm.grubhub.com
operations:
  - getBusyMode
  - setBusyMode
  - updateBusyMode
  - deleteActiveBusyMode
  - openNow
  - closeNow
  - getRepeatingSchedule
  - putRepeatingSchedule
  - getScheduledOverrides
  - overrideSchedule
  - deleteScheduleOverride
  - updateMerchantStatusByOrderType
  - updateMerchantStatusByOrderTypeBatch
  - getMerchantStatusByOrderTypeBatchStatus
---

# Keep a Grubhub storefront honest about whether it can cook

Four separate mechanisms control availability, at different time scales. Pick the right one.

| Need | Operation |
|---|---|
| Kitchen is slammed for the next N minutes | `setBusyMode` → `getBusyMode` → `updateBusyMode` → `deleteActiveBusyMode` |
| Stop / start taking orders right now | `closeNow` / `openNow` |
| A one-off closure or special hours on a date | `overrideSchedule` → `deleteScheduleOverride` |
| Regular weekly hours per fulfillment type | `putRepeatingSchedule`, plus `updatePickupSchedule` / `updateDeliverySchedule` / `updateCateringSchedule` |
| Take a merchant (or many) offline entirely | `updateMerchantStatusByOrderType` (`/pos/v2`), `updateMerchantStatusByOrderTypeBatch` |

## Batch status is asynchronous

`PUT /pos/v2/merchant/pos-status` (`updateMerchantStatusByOrderTypeBatch`) returns a batch handle.
Poll `GET /pos/v2/merchant/pos-status/{batch_id}/status`
(`getMerchantStatusByOrderTypeBatchStatus`) until it reports done. A `422` on submit means duplicate
merchant IDs, an empty list, a batch over the (unpublished) maximum, or a merchant blocked from
updates. The maximum batch size is not published — discover it in preprod.

## Conflicts are real and are not transient

- `overrideSchedule` returns `409` "Schedule override overlaps existing override". Read
  `getScheduledOverrides` and delete the overlap before retrying; a blind retry will loop.
- `heartbeatStatusChangeTriggered` returns `409` when the merchant is already in the status you
  asked for. That is success, not failure.
- `openNow` / `closeNow` return `503` "Service requires reconciliation to be enabled" when the
  merchant is not configured for it.

## Note

`/pos/v2/merchant/{merchant_id}/pos-status` supersedes the `/pos/v1` operation of the same shape,
but Grubhub still publishes the v1 operation and does **not** mark it deprecated. Prefer v2.
