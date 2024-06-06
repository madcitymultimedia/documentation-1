# Contributions in the Ledger

## Contributions

1. A contribution will typically include a pair of CONTRIBUTION transactions and a pair of PAYMENT\_PROCESSOR\_FEE transactions.
2. If the contribution is made to a collective that is hosted by a fiscal host and if that host charges a hosting fee then there will also be a pair of HOST\_FEE transactions.
3. If there is a fiscal host and the fiscal host has a revenue share agreement with the platform then there will also be a pair of HOST\_FEE\_SHARE transactions.
4. If HOST\_FEE\_SHARE applies and the payment processor is able, when the contribution is processed, to split the funds and direct part to the fiscal host and another part to the platform then the HOST\_FEE\_SHARE amount is passed directly to the platform. If that is not possible then the entire contribution (minus the payment processor fee) amount is directed to the fiscal host and a pair of HOST\_FEE\_SHARE\_DEBT transactions are also created to account for money owed by the fiscal host to the platform. The debt transactions are later aggregated and used to generate an expense through which the fiscal host pays the platform and the debt is reconciled.

As a result, a single contribution can result in a set of transactions:

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

Find out more about [Platform settlement expenses](https://docs.opencollective.com/help/independent-collectives/manage-independent-collective/money-going-out-expenses#platform-settlement-expenses).&#x20;

## Refunded Contributions

When contributions are refunded, a new transaction group is created. It contains a set of opposite (relative to the contribution itself) transactions:

1. The contribution is returned: debited from the collective and credited to the contributor
2. The host fees are returned: debited from the fiscal host and credited to the collective.
3. The host fee share paid to the platform is returned: is debited from the platform and credited to the fiscal host.
4. The host fee share debt cancelled: debited from the fiscal host and credited to the platform.
5. Payment processor fees transactions are NOT reversed since they are typically not refunded by the payment processors. In such cases fiscal hosts cover the not refunded payment processor fees and this is represented in the ledger with a pair of PAYMENT\_PROCESSOR\_COVER transactions.

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

As a result, the ledger footprint of a refunded contribution includes:

1. The contribution transactions are one transaction group.
2. The refund transactions are a second transaction group.
3. Relationships between the transactions in the two transaction groups. Each transaction in the contribution transaction group (except the payment processor fees) will have a Refund Transaction ID that points to the opposite transaction in the refund transaction group.
4. The contribution transactions will be marked as REFUNDED.
5. The related refund transactions will be marked as REFUND.

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

It is possible to imagine these two transaction sets existing side by side:

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

## Perspectives of Refunded Contributions

From a contributor perspective a refunded contributions looks like a straightforward pair of opposite transactions - a debit when the contribution was made and a credit when it was refunded.

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

From a collective perspective a refunded contribution looks slightly less symmetric because the PAYMENT PROCESSOR FEE transaction is not refunded and is instead reflected by the PAYMENT PROCESS COVER transaction:

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

From a fiscal host “Operational Funds” perspective a refunded contribution looks symmetrical except for the PAYMENT PROCESSOR COVER transaction:

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

From a fiscal host “Managed Funds” perspective a refunded contribution looks the same as it does from a collective perspective:

<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

## Disputed Contributions

A dispute occurs when a contributor files a complaint with a payment processor (usually because of suspected fraud). If a dispute is settled in favor of the fiscal host the contribution transactions in the ledger remain unchanged. If a dispute is settled in favor of a contributor the transaction will be refunded (and refund transactions will be created in the ledger).

Regardless of the dispute outcome, payment processors charge a dispute fee (paid by the fiscal host) which is recorded in the platform as an additional pair of PAYMENT\_PROCESSOR\_DISPUTE\_FEE transactions:

<figure><img src="../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>
