# API

## GraphQL API

The future of the Open Collective API is our public GraphQL API. You can check the documentation on [https://graphql-docs-v2.opencollective.com](https://graphql-docs-v2.opencollective.com/).

Learn more about it here:\
[https://medium.com/open-collective/open-collective-graphql-api-preview-3b42ed1d55ff](https://medium.com/open-collective/open-collective-graphql-api-preview-3b42ed1d55ff)

## REST API

Our REST API is still supported but we're not working on it anymore.

* [Members](members.md)
  * Get list of members
* [Collectives](collectives.md)
  * Get collective info
  * Get members
  * Get members per tier
  * Get transactions from collective



## PDF Service

The PDF service supports passing either a `Personal-Token` (for personal tokens) or an `Authorization` header (for OAuth).&#x20;

**Getting the receipt for a contribution**

```
GET https://pdf.opencollective.com/receipts/transactions/:transactionUUID/receipt.pdf
```

**Getting the PDF for an Invoice Expense**

```
GET https://pdf.opencollective.com/expense/:expenseUUID/invoice.pdf
```

**Getting a bundled receipt for a fiscal host/period**

```
GET https://pdf.opencollective.com/receipts/collectives/:fromCollective/:host/:fromDate/:toDate/receipt.pdf
```
