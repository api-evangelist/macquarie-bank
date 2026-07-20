---
name: List Macquarie Bank public products
description: Retrieve Macquarie Bank's publicly offered banking products and their detail via the unauthenticated CDR Product Reference Data API.
api: openapi/macquarie-bank-cds-banking-products-openapi.yml
operations: [listBankingProducts, getBankingProductDetail]
---

# List Macquarie Bank public products

This is the **public, unauthenticated** CDR Product Reference Data surface. No
OAuth token is required — only the mandatory CDS version header.

## Base URL
`https://api.macquariebank.io/cds-au/v1/banking`

## Rules
- Always send the `x-v` header (e.g. `x-v: 3`). Omitting it returns HTTP 400
  `urn:au-cds:error:cds-all:Header/Missing` (confirmed live).
- Responses wrap payloads in `{ data, links, meta }`. Page through lists with
  `page` / `page-size`; read `meta.totalPages` to bound iteration.
- Errors use the CDS envelope `{ "errors": [ { code, title, detail } ] }`, not
  RFC 9457. See `errors/macquarie-bank-problem-types.yml`.

## Steps
1. Call `listBankingProducts` (`GET /banking/products`) with `x-v: 3`. Optionally
   filter with `product-category`, `effective`, and paginate via `page`/`page-size`.
   Read `data.products[]` and follow `links.next` until exhausted.
2. For a product of interest, call `getBankingProductDetail`
   (`GET /banking/products/{productId}`) with the `productId` from step 1 to read
   rates, fees, features and eligibility.
