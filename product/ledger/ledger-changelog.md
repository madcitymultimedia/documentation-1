# Ledger Changelog

## January 2024: Separate payment processor fees and taxes&#x20;

_From January 2024 payment processor fees and taxes were separated from the transaction record in the ledger._ \


Over the last couple of years, we’ve received feedback from fiscal hosts and accountants that has prompted us to make a change to the ledger to make more it more consistent and future proof. We’ve modified the ledger so that payment processor fees and taxes are recorded as separate transactions.&#x20;

_This is how payment processor fees and taxes were represented in the ledger until now, as fields/properties of a transaction:_

<table><thead><tr><th width="110">type</th><th>kind</th><th width="91">amount</th><th width="205">paymentProcessorFee</th><th>netAmount</th></tr></thead><tbody><tr><td>CREDIT</td><td>CONTRIBUTION</td><td>100</td><td>1.8</td><td>98.2</td></tr></tbody></table>

_For contributions or expenses made after January 2024, separate transactions will be recorded for payment processor fees and taxes. For example:_

<table><thead><tr><th width="113">type</th><th width="475">kind</th><th>amount</th></tr></thead><tbody><tr><td>CREDIT</td><td>CONTRIBUTION</td><td>100</td></tr><tr><td>DEBIT</td><td>PAYMENT_PROCESSOR_FEE</td><td>-1.8</td></tr></tbody></table>

### CSV Export Backwards Compatibility

The default export configuration hasn’t changed and still includes a column for payment processor fees. However, from 2024, payment processor fees are exported as separate transactions and the payment processor fee column will be set to zero. If you need to continue to export data (from the 1st of January 2024 and onward) with payment processor fees as a column (instead of separate transactions) enable the “Separate transactions compatibility” option. This will convert the newly separated payment processor fee transactions back into transaction columns.\


<figure><img src="../../.gitbook/assets/Screenshot 2024-03-27 at 13.37.48.png" alt=""><figcaption></figcaption></figure>

### Dashboard Transactions List

In the dashboard transactions tool the new transactions (for payment processor fees and taxes) will appear as separate transactions. In this screenshot the blue line on the right hand side of the table is a visual indicator for a group of related transactions. Here you can see that a (now separate) Payment processor fee transaction is related to the contribution transaction.

<figure><img src="../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

You can also filter to see only those transactions using the “kind” filter:![image.png](https://codahosted.io/docs/nHLKv7oLV0/blobs/bl-a\_8VsiohRJ/8db97f2bf4c53a65089ac0c0e659a085e3dd50189d642615770b1e11cdcabab81739779d5e4c409cfa12e16b00be0dc9e8914e0477a7ee9d4631bda5763d43a3260073d930ca292e4fb9f89a74c8e4922f6814a2150c5cb9d8f7fd4c24512ddab7d15f3b)

