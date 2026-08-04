# Macquarie Bank (macquarie-bank)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Macquarie Bank Limited is an Australian authorised deposit-taking institution (ADI) and the retail and business banking arm of Macquarie Group Limited, the ASX-listed (ASX:MQG) global financial services group headquartered in Sydney. It is a wholly-owned, shareholder-owned subsidiary of a publicly listed parent (not a mutual). As a designated CDR / Open Banking data holder, it exposes a public, unauthenticated Product Reference Data API conforming to the Consumer Data Standards (CDS), alongside consumer-authorised data sharing and a registered developer portal.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/macquarie-bank/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/macquarie-bank/refs/heads/main/apis.yml)

## Tags

- Financial
- Banks
- Open Banking
- CDR
- Consumer Data Right
- Consumer Banking
- Australia
- Product Reference Data
- Payments

## Timestamps

- **Created:** 2026-07-20
- **Modified:** 2026-07-20

## APIs

### Macquarie Bank CDR Product Reference Data API

Public, unauthenticated Consumer Data Right Product Reference Data API. Get Products and Get Product Detail return Macquarie Bank Limited's publicly offered banking products (transaction and savings accounts, residential mortgages, credit and charge cards, term deposits, overdrafts, business loans, regulated trust accounts) conforming to the DSB Consumer Data Standards. Confirmed live returning HTTP 200 with an `x-v` response header and a `data.products` array (21 products at time of review).

- **Human URL:** [https://www.macquarie.com.au/digital-banking/open-banking.html](https://www.macquarie.com.au/digital-banking/open-banking.html)
- **Base URL:** `https://api.macquariebank.io/cds-au/v1/banking`

#### Tags

- CDR
- Open Banking
- Product Reference Data
- Banking Products
- Public

#### Properties

- [Documentation](https://www.macquarie.com.au/digital-banking/open-banking.html)
- [API Reference](https://consumerdatastandardsaustralia.github.io/standards/#cdr-banking-api_banking-apis_get-products)
- [OpenAPI](openapi/macquarie-bank-cds-banking-products-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Macquarie Bank CDR Discovery Status API

Public, unauthenticated Consumer Data Standards discovery endpoints (`GET /discovery/status` and `GET /discovery/outages`) that publish the availability and planned outages of Macquarie Bank's CDR data holder implementation. `GET /discovery/status` confirmed live returning HTTP 200.

- **Human URL:** [https://www.macquarie.com.au/digital-banking/open-banking.html](https://www.macquarie.com.au/digital-banking/open-banking.html)
- **Base URL:** `https://api.macquariebank.io/cds-au/v1/discovery`

#### Tags

- CDR
- Open Banking
- Discovery
- Status
- Public

#### Properties

- [API Reference](https://consumerdatastandardsaustralia.github.io/standards/#common-apis_common-apis_get-status)
- [OpenAPI](openapi/macquarie-bank-cds-banking-products-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Macquarie Bank CDR Banking Data Sharing API

Consumer-authorised CDR banking data sharing (accounts, balances, transactions, payees, direct debits, scheduled payments) exposed per the DSB Consumer Data Standards. Access requires CDR accreditation as an Accredited Data Recipient and consumer consent, secured with the CDR OAuth2 / OpenID Connect (FAPI-based) security profile over MTLS — not an openly callable endpoint.

- **Human URL:** [https://www.macquarie.com.au/digital-banking/open-banking.html](https://www.macquarie.com.au/digital-banking/open-banking.html)
- **Base URL:** `https://api.macquariebank.io/cds-au/v1/banking`

#### Tags

- CDR
- Open Banking
- Data Sharing
- Accounts
- Transactions
- Authenticated

#### Properties

- [Documentation](https://www.macquarie.com.au/digital-banking/open-banking.html)
- [API Reference](https://consumerdatastandardsaustralia.github.io/standards/#cdr-banking-api)
- [OpenAPI](openapi/macquarie-bank-cds-banking-products-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Macquarie DEFT Payments API

Macquarie's DEFT payments platform, surfaced through the registered Macquarie developer portal, lets businesses build branded payment experiences with tokenised credit card, bank account and direct debit APIs, payment schedules and one-off payments. Documentation and access require registration through the developer portal (no unauthenticated public base URL is published).

- **Human URL:** [https://developer.macquariebank.io/devportal/](https://developer.macquariebank.io/devportal/)

#### Tags

- Payments
- Direct Debit
- Developer Portal
- Business Banking

#### Properties

- [Developer Portal](https://developer.macquariebank.io/devportal/)
- [Documentation](https://www.macquarie.com.au/help/business/deft.html)

## Common Properties

- [Website](https://www.macquarie.com.au/)
- [Developer Portal](https://developer.macquariebank.io/devportal/)
- [Documentation](https://www.macquarie.com.au/digital-banking/open-banking.html)
- [LinkedIn](https://www.linkedin.com/company/macquarie-group/)
- [CDR Register](https://www.cdr.gov.au/find-a-provider)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
