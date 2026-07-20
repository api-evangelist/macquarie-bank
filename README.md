# Macquarie Bank (macquarie-bank)

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
