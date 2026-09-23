---
name: grubhub-merchant-onboarding
description: Refer, check eligibility for, activate, associate and deactivate merchants on Grubhub through the partner Onboarding API, and report an onboarding issue.
api: Grubhub Onboarding API
generated: '2026-09-17'
method: generated
source: openapi/grubhub-onboarding-openapi.yml
base_url: https://api-third-party-gtm.grubhub.com
operations:
  - getEligibleMerchants
  - referralSignup
  - activateMerchants
  - partnerActivateMerchants
  - associateMerchants
  - deactivate
  - partnerDeactivate
  - triage
---

# Onboard a merchant onto your Grubhub integration

This is the one Grubhub surface where `X-GH-PARTNER-KEY` is `required: true` in the contract, typed
as a UUID. The Onboarding document also states in prose that association and deactivation are
validated "using Oauth2" — the authorization server is real and discoverable at
`https://api-gtm.grubhub.com/.well-known/oauth-authorization-server`, but no operation in the
document declares a security requirement, so you will need the partner onboarding guide for the
exact token flow.

## Steps

1. **List who you may act on.** `GET /merchant/onboarding/v1/merchants` (`getEligibleMerchants`).
   Takes `page` and `size`; `400` means they are not valid numbers, `422` means `page < 1`,
   `size < 1`, or `size` above the unpublished maximum.
2. **Refer a restaurant that is not on Grubhub yet.**
   `POST /merchant/onboarding/v1/referral` (`referralSignup`) → `ReferralResponse`. A `400` carries
   the input-validation detail in that same schema.
3. **Associate an existing merchant with your integration.**
   `POST /merchant/onboarding/v1/associate` (`associateMerchants`). `404` = merchant not found,
   `422` = malformed request.
4. **Activate.** `POST /merchant/onboarding/v1/activate` (`activateMerchants`), or
   `POST /merchant/onboarding/v1/partner/activate` (`partnerActivateMerchants`) for the
   partner-scoped variant.
5. **Deactivate** with the matching `deactivate` / `partnerDeactivate`. This is the reversal path
   for step 4. **No window is published** — the contract does not say how long after activation a
   deactivation is accepted.
6. **When onboarding stalls,** `POST /merchant/onboarding/v1/triage` (`triage`) files the issue.

## Rules

- No idempotency. A retried `activateMerchants` is a second activation attempt; call
  `getEligibleMerchants` and read state before retrying.
- `400` here means "invalid input **or merchant not eligible**" — the same status covers a
  malformed body and a business rejection. Read the body, not the code.
