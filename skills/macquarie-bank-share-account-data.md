---
name: Share Macquarie Bank account data (CDR)
description: Read a consenting consumer's Macquarie Bank accounts, balances and transactions via the consent-based CDR Banking Data Sharing API.
api: openapi/macquarie-bank-cds-banking-products-openapi.yml
operations: [listBankingAccounts, getBankingBalance, listBankingTransactions, getBankingTransactionDetail]
---

# Share Macquarie Bank account data (CDR)

This is the **consent-based** CDR data-sharing surface. It is NOT openly callable.

## Prerequisites
- CDR **Accredited Data Recipient (ADR)** status registered on the CDR Register.
- A consumer **consent** / authorisation obtained via the CDR OIDC flow.
- **FAPI 1.0 Advanced** security: OAuth2 authorization-code + PKCE, Pushed
  Authorization Requests, `private_key_jwt` client auth, and **MTLS**
  sender-constrained access tokens. See `authentication/macquarie-bank-authentication.yml`
  and scopes in `scopes/macquarie-bank-scopes.yml`.

## Rules
- Send `x-v` on every call; send `x-fapi-interaction-id` for correlation.
- Request only the scopes the consent grants (e.g. `bank:accounts.basic:read`,
  `bank:transactions:read`).
- Errors use the CDS envelope; paginate with `page` / `page-size`.

## Steps
1. `listBankingAccounts` (`GET /banking/accounts`) to enumerate consented accounts.
2. `getBankingBalance` (`GET /banking/accounts/{accountId}/balance`) for a balance.
3. `listBankingTransactions` (`GET /banking/accounts/{accountId}/transactions`),
   filtering by `oldest-time`/`newest-time`; page via `links.next`.
4. `getBankingTransactionDetail`
   (`GET /banking/accounts/{accountId}/transactions/{transactionId}`) for detail.
