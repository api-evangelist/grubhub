---
name: grubhub-menu-ingestion
description: Validate and ingest a normalized restaurant menu into the Grubhub Marketplace, then poll the ingestion job to completion.
api: Grubhub Menu API
generated: '2026-09-17'
method: generated
source: openapi/grubhub-menu-openapi.yml
base_url: https://api-third-party-gtm.grubhub.com
operations:
  - validatePosMenu
  - addOrUpdatePosFullMenu
  - getMenuIngestionStatus
  - findNormalizedMenu
---

# Ingest a Grubhub menu

Menu ingestion is **diff-based**. Grubhub matches, updates, creates and removes menu objects by the
external IDs you send, so the payload you post is the whole intended menu, not a patch.

## Before you start

- Base URL `https://api-third-party-gtm.grubhub.com` (preprod `https://api-third-party-gtm-pp.grubhub.com`).
- Send `X-GH-PARTNER-KEY` (your partner UUID) on every request.
- The payload shape is `PosNormalizedMenu` — see `json-schema/grubhub-posnormalizedmenu-schema.json`.

## Steps

1. **Dry-run the menu.** `POST /pos/v1/menu/ingestion/validate` (`validatePosMenu`) with the full
   `PosNormalizedMenu` body. This validates without ingesting. A `503` means validation timed out —
   resubmit rather than treating it as a rejection.
2. **Submit the menu.** `POST /pos/v1/menu/ingestion` (`addOrUpdatePosFullMenu`). A `409` means an
   ingestion is already in flight for that merchant; do not retry blind — poll the existing job
   first. A `422` means the body was structurally accepted but semantically rejected.
3. **Poll the job.** `GET /pos/v1/menu/ingestion/jobs/{job_id}` (`getMenuIngestionStatus`) until the
   `PosNormalizedMenuUpdateStatus` reports completion. `404` means the job ID does not exist.
4. **Read back what Grubhub stored.** `GET /pos/v1/merchant/{merchant_id}/menu/normalized`
   (`findNormalizedMenu`) and diff it against what you sent.

## Rules this API does not enforce for you

- **There is no idempotency mechanism.** If step 2 times out, do **not** resubmit until you have
  polled; a second submission is a second ingestion.
- **There is no rollback.** No operation restores a previous menu and no menu version is exposed.
  The only way back is to re-ingest the previous menu yourself, so keep it.
- `merchant_id` here is the **legacy** merchant identifier, not `merchant_long_id` used by the
  Orders API. Sending the wrong one returns `404`, not a validation error.
