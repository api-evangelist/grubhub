---
name: grubhub-merchant-reporting
description: Request a merchant export report from Grubhub, wait for the report-status webhook, and fetch the download URL.
api: Grubhub Merchant Reporting API
generated: '2026-09-17'
method: generated
source: openapi/grubhub-reporting-endpoints-openapi.yml, openapi/grubhub-reporting-webhooks-openapi.yml
base_url: https://api-third-party-gtm.grubhub.com
operations:
  - getEnabledMerchants
  - createExportReport
  - getDownloadUrl
---

# Export a Grubhub merchant report

A three-operation asynchronous surface: request, wait, download.

## Steps

1. **Find out who you can report on.** `GET /merchant/reporting/v1/merchants`
   (`getEnabledMerchants`) lists the merchant IDs enabled for reporting under your partner ID.
   `422` means the partner ID is invalid or does not exist.
2. **Request the report.** `POST /merchant/reporting/v1/reports` (`createExportReport`) with a
   `CreateExportReportRequestByPartner` body; you get a `CreateExportReportResponseByPartner`
   carrying the report UUID. A `403` here usually means the Reporting API is not configured for
   your partner account, or the report is not available for the merchants you asked about — that is
   a configuration problem, not a transient failure, so do not retry it.
3. **Wait for the `[Egress] Report Status Update Webhook`** (`MerchantReportStatusWebhook`). This is
   the intended completion signal.
4. **Download.** `GET /merchant/reporting/v1/reports/{reportUuid}` (`getDownloadUrl`) returns a
   `GetDownloadUrlResponseByPartner`. `404` distinguishes "report with given UUID was not found"
   from "URL for report with given UUID was not found" — the second means the report exists but is
   not ready, so go back to waiting.

## Rules

- Errors on this surface use `MerchantReportingErrorResponse`, which carries only `message`. There
  is no error code to branch on.
- No idempotency: a retried `createExportReport` produces a second report, not the same one.
