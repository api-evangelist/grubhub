# grubhub (grubhub)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Grubhub is a US online food-ordering and delivery marketplace connecting diners with local restaurants across Grubhub and Seamless. Its partner platform lets point-of-sale vendors, online-ordering providers, delivery aggregators and enterprise restaurant brands integrate directly: ingest normalized menus, receive and fulfil Marketplace orders, control merchant availability and schedules, run last-mile delivery on Grubhub's national courier network through Grubhub Connect, onboard merchants self-service, and export merchant reports. Grubhub publishes twelve first-party OpenAPI documents covering 91 operations and three egress webhooks from its partner developer portal.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/grubhub/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/grubhub/refs/heads/main/apis.yml)

## Timestamps

- **Modified:** 2026-09-17

## APIs

### Grubhub Menu API

Create, update and manage Grubhub Marketplace menus. Ingestion is diff-based against external IDs: validate a normalized menu, submit it, poll the ingestion job, and read back what Grubhub stored. Also carries menu-item schedule overrides (by internal or external ID, in bulk) and alcohol tagging.

- **Human URL:** [https://developer.grubhub.com/api/menu](https://developer.grubhub.com/api/menu)
- **Base URL:** `https://api-third-party-gtm.grubhub.com`

#### Tags

- Menu
- Menu Ingestion
- Catalog
- Restaurants
- Point of Sale

#### Properties

- [Menu OpenAPI (harvested from Grubhub)](openapi/grubhub-menu-openapi.yml) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI (provider-hosted)](https://developer.grubhub.com/resource/partner-docs/api-docs/menu_api_final.json) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developer.grubhub.com/api/menu)
- [APIReference](https://developer.grubhub.com/api/menu)
- [Overlay](overlays/grubhub-menu-overlay.yaml) — [Overlay specification](https://spec.openapis.org/overlay/latest.html)

### Grubhub Orders API

Receive and manage Grubhub Marketplace orders. Retrieve an order by UUID, list a merchant's or a group's orders by status and date range, advance an order through its status lifecycle, raise and poll order change requests, and attach pickup instructions. New orders arrive by webhook; polling is the fallback.

- **Human URL:** [https://developer.grubhub.com/api/orders](https://developer.grubhub.com/api/orders)
- **Base URL:** `https://api-third-party-gtm.grubhub.com`

#### Tags

- Orders
- Order Management
- Marketplace
- Restaurants
- Point of Sale

#### Properties

- [Orders OpenAPI (harvested from Grubhub)](openapi/grubhub-orders-openapi.yml) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI (provider-hosted)](https://developer.grubhub.com/resource/partner-docs/api-docs/order_api_final.json) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developer.grubhub.com/api/orders)
- [APIReference](https://developer.grubhub.com/api/orders)
- [Overlay](overlays/grubhub-orders-overlay.yaml) — [Overlay specification](https://spec.openapis.org/overlay/latest.html)
- [AsyncAPI](asyncapi/grubhub-order-events-asyncapi.yml) — [AsyncAPI specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Webhooks](asyncapi/grubhub-webhooks.yml)

### Grubhub Merchant Data API

Read and maintain merchant configuration on Grubhub: profile, tax rate, delivery minimum, delivery boundaries and area fees, fulfillment estimates, pre-order window, scheduled-ordering opt-in, and online/offline status by order type. Batch writes return a batch handle that is polled to completion.

- **Human URL:** [https://developer.grubhub.com/api/merchant-data](https://developer.grubhub.com/api/merchant-data)
- **Base URL:** `https://api-third-party-gtm.grubhub.com`

#### Tags

- Merchants
- Merchant Data
- Configuration
- Restaurants
- Store Management

#### Properties

- [Merchant Data OpenAPI (harvested from Grubhub)](openapi/grubhub-merchant-data-openapi.yml) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI (provider-hosted)](https://developer.grubhub.com/resource/partner-docs/api-docs/merchant_data_api_final.json) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developer.grubhub.com/api/merchant-data)
- [APIReference](https://developer.grubhub.com/api/merchant-data)
- [Overlay](overlays/grubhub-merchant-data-overlay.yaml) — [Overlay specification](https://spec.openapis.org/overlay/latest.html)

### Grubhub Merchant Schedules API

Manage restaurant operating hours on Grubhub: repeating weekly schedules for delivery, pickup and catering, one-off schedule overrides for closures and special hours, and immediate open-now / close-now control.

- **Human URL:** [https://developer.grubhub.com/api/merchant-schedules](https://developer.grubhub.com/api/merchant-schedules)
- **Base URL:** `https://api-third-party-gtm.grubhub.com`

#### Tags

- Schedules
- Availability
- Hours
- Restaurants
- Store Management

#### Properties

- [Merchant Schedules OpenAPI (harvested from Grubhub)](openapi/grubhub-merchant-schedules-openapi.yml) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI (provider-hosted)](https://developer.grubhub.com/resource/partner-docs/api-docs/merchant_schedule_api_final.json) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developer.grubhub.com/api/merchant-schedules)
- [APIReference](https://developer.grubhub.com/api/merchant-schedules)
- [Overlay](overlays/grubhub-merchant-schedules-overlay.yaml) — [Overlay specification](https://spec.openapis.org/overlay/latest.html)

### Grubhub Busy Intervals API

Mark a restaurant as busy for a bounded interval so Grubhub extends quoted times or pauses new orders, then read, update or clear the active interval.

- **Human URL:** [https://developer.grubhub.com/api/busy-intervals](https://developer.grubhub.com/api/busy-intervals)
- **Base URL:** `https://api-third-party-gtm.grubhub.com`

#### Tags

- Availability
- Busy Mode
- Operations
- Restaurants
- Store Management

#### Properties

- [Busy Intervals OpenAPI (harvested from Grubhub)](openapi/grubhub-busy-intervals-openapi.yml) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI (provider-hosted)](https://developer.grubhub.com/resource/partner-docs/api-docs/busy_mode_api_final.json) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developer.grubhub.com/api/busy-intervals)
- [APIReference](https://developer.grubhub.com/api/busy-intervals)
- [Overlay](overlays/grubhub-busy-intervals-overlay.yaml) — [Overlay specification](https://spec.openapis.org/overlay/latest.html)

### Grubhub Deliveries API

Read the delivery state of a Grubhub Marketplace order, by order UUID or by delivery ID. The only operation in the whole Grubhub contract that declares a 429 lives here.

- **Human URL:** [https://developer.grubhub.com/api/deliveries](https://developer.grubhub.com/api/deliveries)
- **Base URL:** `https://api-third-party-gtm.grubhub.com`

#### Tags

- Deliveries
- Delivery Tracking
- Logistics
- Restaurants
- Last Mile

#### Properties

- [Deliveries OpenAPI (harvested from Grubhub)](openapi/grubhub-deliveries-openapi.yml) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI (provider-hosted)](https://developer.grubhub.com/resource/partner-docs/api-docs/delivery_api_final.json) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developer.grubhub.com/api/deliveries)
- [APIReference](https://developer.grubhub.com/api/deliveries)
- [Overlay](overlays/grubhub-deliveries-overlay.yaml) — [Overlay specification](https://spec.openapis.org/overlay/latest.html)

### Grubhub Connect (Delivery as a Service) API

Grubhub Connect is delivery-as-a-service on Grubhub's national courier network for aggregators, marketplaces and enterprise merchants. Request and accept delivery quotes, check service areas, track status, update dropoff and pickup verification, mint a masked courier proxy phone number, increase a courier tip, cancel a delivery and request a refund - plus a full production-safe test path.

- **Human URL:** [https://developer.grubhub.com/api/daas-endpoints](https://developer.grubhub.com/api/daas-endpoints)
- **Base URL:** `https://api-third-party-gtm.grubhub.com`

#### Tags

- Delivery
- Logistics
- Last Mile
- Couriers
- Delivery as a Service

#### Properties

- [Grubhub Connect Endpoints OpenAPI (harvested from Grubhub)](openapi/grubhub-connect-endpoints-openapi.yml) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI (provider-hosted)](https://developer.grubhub.com/resource/partner-docs/api-docs/daas_api_final.json) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developer.grubhub.com/api/daas-endpoints)
- [APIReference](https://developer.grubhub.com/api/daas-endpoints)
- [Overlay](overlays/grubhub-connect-endpoints-overlay.yaml) — [Overlay specification](https://spec.openapis.org/overlay/latest.html)

### Grubhub Connect Webhooks

The egress event contract for Grubhub Connect, published as an OpenAPI 3.1.0 webhooks-only document: Delivery Status Update (Created, Assigned, Unassigned, CourierAtPickup, PickedUp, InTransit, CourierAtDropoff, Delivered, Canceled, ReturnInitiated, ReturnCompleted) and Delivery Refund Update.

- **Human URL:** [https://developer.grubhub.com/api/daas-webhooks](https://developer.grubhub.com/api/daas-webhooks)
- **Base URL:** `https://api-third-party-gtm.grubhub.com`

#### Tags

- Webhooks
- Events
- Delivery
- Logistics
- Event Driven

#### Properties

- [Grubhub Connect Webhooks OpenAPI (harvested from Grubhub)](openapi/grubhub-connect-webhooks-openapi.yml) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI (provider-hosted)](https://developer.grubhub.com/resource/partner-docs/api-docs/daas_webhooks_final.json) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developer.grubhub.com/api/daas-webhooks)
- [APIReference](https://developer.grubhub.com/api/daas-webhooks)
- [Overlay](overlays/grubhub-connect-webhooks-overlay.yaml) — [Overlay specification](https://spec.openapis.org/overlay/latest.html)
- [AsyncAPI](asyncapi/grubhub-delivery-events-asyncapi.yml) — [AsyncAPI specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Webhooks](asyncapi/grubhub-webhooks.yml)

### Grubhub Onboarding API

Self-service merchant onboarding for partners: list eligible merchants, refer a restaurant that is not yet on Grubhub, associate an existing merchant with the integration, activate and deactivate merchants (partner-scoped variants included), and file an onboarding issue for triage.

- **Human URL:** [https://developer.grubhub.com/api/onboarding](https://developer.grubhub.com/api/onboarding)
- **Base URL:** `https://api-third-party-gtm.grubhub.com`

#### Tags

- Onboarding
- Merchants
- Provisioning
- Partners
- Restaurants

#### Properties

- [Onboarding OpenAPI (harvested from Grubhub)](openapi/grubhub-onboarding-openapi.yml) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI (provider-hosted)](https://developer.grubhub.com/resource/partner-docs/api-docs/onboarding_api_final.json) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developer.grubhub.com/api/onboarding)
- [APIReference](https://developer.grubhub.com/api/onboarding)
- [Overlay](overlays/grubhub-onboarding-overlay.yaml) — [Overlay specification](https://spec.openapis.org/overlay/latest.html)

### Grubhub Merchant Reporting API

Asynchronous merchant report export: list the merchants enabled for reporting under a partner ID, request a report, and fetch its download URL once the report-status webhook fires.

- **Human URL:** [https://developer.grubhub.com/api/reporting-endpoints](https://developer.grubhub.com/api/reporting-endpoints)
- **Base URL:** `https://api-third-party-gtm.grubhub.com`

#### Tags

- Reporting
- Analytics
- Exports
- Merchants
- Restaurants

#### Properties

- [Reporting Endpoints OpenAPI (harvested from Grubhub)](openapi/grubhub-reporting-endpoints-openapi.yml) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI (provider-hosted)](https://developer.grubhub.com/resource/partner-docs/api-docs/reporting_api_final.json) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developer.grubhub.com/api/reporting-endpoints)
- [APIReference](https://developer.grubhub.com/api/reporting-endpoints)
- [Overlay](overlays/grubhub-reporting-endpoints-overlay.yaml) — [Overlay specification](https://spec.openapis.org/overlay/latest.html)

### Grubhub Reporting Webhooks

The egress event contract for merchant report exports, published as an OpenAPI 3.1.0 webhooks-only document: Report Status Update. This is the intended completion signal for a requested report.

- **Human URL:** [https://developer.grubhub.com/api/reporting-webhooks](https://developer.grubhub.com/api/reporting-webhooks)
- **Base URL:** `https://api-third-party-gtm.grubhub.com`

#### Tags

- Webhooks
- Events
- Reporting
- Event Driven
- Merchants

#### Properties

- [Reporting Webhooks OpenAPI (harvested from Grubhub)](openapi/grubhub-reporting-webhooks-openapi.yml) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI (provider-hosted)](https://developer.grubhub.com/resource/partner-docs/api-docs/reporting_webhooks_final.json) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developer.grubhub.com/api/reporting-webhooks)
- [APIReference](https://developer.grubhub.com/api/reporting-webhooks)
- [Overlay](overlays/grubhub-reporting-webhooks-overlay.yaml) — [Overlay specification](https://spec.openapis.org/overlay/latest.html)
- [AsyncAPI](asyncapi/grubhub-reporting-events-asyncapi.yml) — [AsyncAPI specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Webhooks](asyncapi/grubhub-webhooks.yml)

### Grubhub Testing API

Grubhub ships its partner test surface as part of the published contract: create a transmission test, simulate a just-in-time order event, and create a test delivery against a preproduction merchant.

- **Human URL:** [https://developer.grubhub.com/api/testing](https://developer.grubhub.com/api/testing)
- **Base URL:** `https://api-third-party-gtm.grubhub.com`

#### Tags

- Testing
- Sandbox
- Developer Experience
- Simulation
- Restaurants

#### Properties

- [Testing OpenAPI (harvested from Grubhub)](openapi/grubhub-testing-openapi.yml) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI (provider-hosted)](https://developer.grubhub.com/resource/partner-docs/api-docs/test_api_final.json) — [OpenAPI specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developer.grubhub.com/api/testing)
- [APIReference](https://developer.grubhub.com/api/testing)
- [Overlay](overlays/grubhub-testing-overlay.yaml) — [Overlay specification](https://spec.openapis.org/overlay/latest.html)
- [Sandbox](sandbox/grubhub-sandbox.yml)

## Common Properties

- [Website](https://www.grubhub.com)
- [DeveloperPortal](https://developer.grubhub.com/)
- [Documentation](https://developer.grubhub.com/)
- [APIReference](https://developer.grubhub.com/api/menu)
- [GettingStarted](https://developer.grubhub.com/get-started)
- [Support](https://get.grubhub.com/help-center/)
- [HelpCenter](https://get.grubhub.com/contact/)
- [Pricing](https://get.grubhub.com/grubhub-pricing-and-fees/)
- [SignUp](https://restaurant.grubhub.com/login/)
- [TermsOfService](https://www.grubhub.com/legal/terms-of-use)
- [PrivacyPolicy](https://www.grubhub.com/legal/privacy-policy)
- [GitHubOrganization](https://github.com/GrubhubProd)
- [LinkedIn](https://www.linkedin.com/company/grubhub-seamless)
- [Blog](https://get.grubhub.com/blog/)
- [BlogRSS](https://get.grubhub.com/blog/feed/)
- [Authentication](authentication/grubhub-authentication.yml)
- [OAuthScopes](scopes/grubhub-scopes.yml)
- [WellKnown](well-known/grubhub-well-known.yml)
- [Conventions](conventions/grubhub-conventions.yml)
- [ErrorCatalog](errors/grubhub-problem-types.yml)
- [DataModel](data-model/grubhub-data-model.yml)
- [Lifecycle](lifecycle/grubhub-lifecycle.yml)
- [Sandbox](sandbox/grubhub-sandbox.yml)
- [Conformance](conformance/grubhub-conformance.yml)
- [Packages](packages/grubhub-packages.yml)
- [LLMsTxt](llms/grubhub-llms.txt)
- [AgentSkill](skills/_index.yml)
- [Webhooks](asyncapi/grubhub-webhooks.yml)
- [AsyncAPI](asyncapi/grubhub-delivery-events-asyncapi.yml)
- [AgenticAccess](agentic-access/grubhub-agentic-access.yml)
- [DomainSecurity](security/grubhub-domain-security.yml)
- [RateLimits](rate-limits/grubhub-rate-limits.yml)
- [Plans](plans/grubhub-plans-pricing.yml)
- [FinOps](finops/grubhub-finops.yml)
- [Vocabulary](vocabulary/grubhub-vocabulary.yml)
- [Rules](rules/grubhub-spectral-rules.yml)
- [JSONLD](json-ld/grubhub-context.jsonld)
- [JSONSchema](json-schema/grubhub-posorder-schema.json)
- [JSONSchema](json-schema/grubhub-posnormalizedmenu-schema.json)
- [JSONSchema](json-schema/grubhub-posmerchantdata-schema.json)
- [JSONSchema](json-schema/grubhub-delivery-schema.json)

## Notes

- The twelve OpenAPI documents in `openapi/` were fetched verbatim on 2026-09-17 from Grubhub's own
  developer portal at `https://developer.grubhub.com/resource/partner-docs/api-docs/`. The raw JSON as
  served is kept in `openapi/_harvested/`.
- Grubhub publishes no client SDK, no MCP server, no A2A agent card, no CLI, no public status page and
  no changelog. Those absences are recorded in the artifacts rather than filled in.
