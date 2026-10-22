---
name: macquarie-bank-review-payment-obligations
description: Review a consenting consumer's Macquarie Bank payees, direct debits, scheduled payments and instalment plans via the consent-based CDR Banking Data Sharing API.
api:
- openapi/macquarie-bank-banking-payees-api-openapi.yml
- openapi/macquarie-bank-banking-account-direct-debits-api-openapi.yml
- openapi/macquarie-bank-banking-account-scheduled-payments-api-openapi.yml
operations: [listBankingPayees, getBankingPayeeDetail, listDirectDebits, listScheduledPayments, listInstalmentPlans]
---

# Review Macquarie Bank payment obligations (CDR)

Consent-gated: requires CDR Accredited Data Recipient status, a consumer consent
with the matching scopes, and FAPI 1.0 Advanced OAuth over MTLS (see
`authentication/macquarie-bank-authentication.yml`, `scopes/macquarie-bank-scopes.yml`).
All operations are read-only GETs, so idempotency keys are not needed.

## Rules
- Send `x-v` on every call; send `x-fapi-interaction-id` for correlation.
- Page lists with `page` / `page-size` and follow `links.next`.
- Errors use the CDS `{ "errors": [ { code, title, detail } ] }` envelope.

## Steps
1. `listBankingPayees` (`GET /banking/payees`), then `getBankingPayeeDetail`
   (`GET /banking/payees/{payeeId}`) for a payee's detail.
2. For each consented account (from `listBankingAccounts`), call `listDirectDebits`
   (`GET /banking/accounts/{accountId}/direct-debits`).
3. `listScheduledPayments` (`GET /banking/accounts/{accountId}/payments/scheduled`).
4. `listInstalmentPlans` (`GET /banking/accounts/{accountId}/payments/plans`).
5. For many accounts, the bulk variants `listDirectDebitsBulk`, `listScheduledPaymentsBulk`
   and `listInstalmentPlansBulk` cover all consented accounts in one call.
