---
description: "A log of changes. Breaking changes will be denoted with \U0001F6A8"
---

# Changelog

## March 28, 2020

### New

* Pagination options for [GET /v1/transactions](transactions/get-all-transactions.md) \(`limit` and `offset`\)
* Filter options for [GET /v1/transactions](transactions/get-all-transactions.md) \(`asset_id`, `recurring_id`, `plaid_account_id`, `tag_id`, `category_id`\)
* New endpoint: [GET /v1/tags](tags/get-all-tags.md)

### Changed

* Support for tags in [PUT /v1/transactions/:id](transactions/update-transaction.md) and [POST /v1/transactions](transactions/insert-transactions.md)
* \*\*\*\*[**🚨**](https://emojipedia.org/police-car-light/)Split object for [splitting transactions](transactions/update-transaction.md) is moved out of the Transactions object and to a higher-level. We will still support the `split` property for a few more weeks before removing it completely.



