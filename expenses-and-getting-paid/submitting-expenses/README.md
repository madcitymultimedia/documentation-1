# Submitting Expenses

Go to the Collective you're submitting the expense to and click "Submit Expense".

![](../../.gitbook/assets/expenses\_submitting\_expenses\_2021-05-31.png)

On the **Submit expense** page, you can submit two types of expenses, **reimbursements** and **invoices.** On this page, you can also check the **Collective balance**, review **expense policies** and get the answers to a few of the most frequently asked questions.

![Expense submission page](../../.gitbook/assets/expenses-and-getting-paid\_submitting-expenses\_typical-page-scheme\_2020-05-11.png)

### Payee information

In the first step, you can specify who will be paid for this expense (an individual or an organization) and which payment method you wish to use.

If you are invoicing through a company, create an organization profile for your company and select it here instead of using your personal profile, so the correct entity is recorded as being paid for tax purposes.

Additionally, the invoice form will ask for your country, physical address, and give you the option to add more info.

![Additional info requested by the invoice form](../../.gitbook/assets/expenses-and-getting-paid\_submitting-expenses\_invoice-additional-info\_2020-05-12.png)

The availability of certain options depends on which plan the organization adopts, and may include **PayPal**, **wire transfers**, or a **custom method**.

#### PayPal

To use **PayPal**, you can either select one of the saved PayPal accounts or add a new one by adding the email address registered in said account.

#### Wire transfers

You can either select a saved bank account or add a new one. To add a new bank account:

1. Select the currency in which you would like to receive your payment.
2. Fill all fields with the requested info, making sure to not use any acronyms. **All fields are mandatory** and may vary depending on the selected currency.

Our bank transfer feature uses TransferWise and is only available in countries TransferWise serves. For an up-to-date list of countries, please refer [to their website](https://transferwise.com).

#### Custom payment method

Add any relevant info necessary to complete the transaction.

{% hint style="warning" %}
In order to be paid, submitted expenses must be approved by a Collective admin, who ensures valid use of the Collective's funds. Then it proceeds to the fiscal host admin for processing.
{% endhint %}

### Reimbursements

A **reimbursement** allows you to be reimbursed for a purchase you already made. To open the submission form, click on **Reimbursement** and add a title to your expense.

![](../../.gitbook/assets/expenses-and-getting-paid\_submitting-expenses\_reimbursement-form\_2020-05-11.gif)

#### Adding receipts

Reimbursements must have receipts. Upload one or multiple receipts by dragging and dropping files or opening the file selector. Describe each item and add the date of purchase and amount spent.

A **valid receipt** contains:

1. Name of the vendor (person or company you paid) &#x20;
2. Transaction date (when you paid) &#x20;
3. A detailed description of goods or services purchased (what you bought) &#x20;
4. Amount paid &#x20;
5. Form of payment (cash, check, or last four digits of the credit card)

![](../../.gitbook/assets/expenses-and-getting-paid\_submitting-expenses\_reimbursement-receipt\_2020-05-11.png)

### Invoices

{% hint style="info" %}
**Private information provided on invoices is not viewable publicly**. The expense amount and title will be listed on the Collective's public page, but the attached files and payment details are only visible to admins.
{% endhint %}

An **invoice** allows you to be paid for your work, or to get funds in advance of a purchase. If you don't have a receipt for a reimbursement, you can submit an invoice instead.

To open the submission form, click on **Invoice** and add a title to your expense.

![](../../.gitbook/assets/expenses-and-getting-paid\_submitting-expenses\_invoice-form\_2020-05-12.gif)

If you have an invoice ready, you can upload it as an attachment to the expense. However, you are still required to set invoice details such as description, date and amount.

If you don't upload an invoice, the expense itself functions as an invoice for accounting purposes, as it contains all required information.

### Expense summary

The Expense summary provides you with an overview of the expense to be submitted, including attached files, items being paid for, payout preferences, etc. The summary allows you to review all info and quickly edit it if needed by clicking on **Edit expense**.

For invoices, the expense summary serves as the official invoice document. You can download it for your accounting records if you wish.

You can also add a private note to the admins. Once your expense is ready, click on **Submit expense**.

### Recurring Expenses

{% hint style="info" %}
**Closed Beta:** This feature is only available on selected collectives.
{% endhint %}

In the _**Expense Summary**_, you can also enable recurrency for your Expense, which will submit the filled expense and automatically create a draft of the same expense after the selected _**Frequency**_.

![](<../../.gitbook/assets/image (48) (1).png>)

Recurring expenses work by automatically creating a new Expense draft and sending it to the author of the expense at the turn of the selected frequency. A draft notification is sent to the author, which can then review, edit and submit another expense.

These drafts are created based on the previous Expense submitted in the same group, this means that each edit you do in the previous draft will be persisted and used for the next one.

It is also possible to set an _**End Date**_ for this recurring expense, which can be useful for setting up reminders for pre-defined contracts.

While editing a new draft, you'll also see a banner displaying information about the recurring nature of the expense:

![](<../../.gitbook/assets/image (51).png>)

You can also cancel any recurring expense, just click on _**Edit details**_ in the recurring expense information banner and later, click on the _**Cancel Recurring Expense**_ button. Done, this draft is now deleted and you'll no longer receive recurring drafts about this expense.

![](<../../.gitbook/assets/image (49) (1).png>)

### Multi-Currency Expenses

You can now submit expenses in multiple currencies. This is useful if the collective operates in USD for example but you want to receive a different currency.

This feature enables you to submit your expense in your preferred currency, a currency conversion rate is then predicted in order to convert the amount to the currency held by the collective. You will receive the full amount submitted on your invoice even if the conversion rate were to change.&#x20;

{% embed url="https://www.loom.com/share/a6f4f8a0455343f3980002473811cf56" %}

#### Supported Currencies&#x20;

* Wise: Collective currency or payout method currency, with the limitation of the currencies that are supported by Wise
* PayPal: [any currency supported by PayPal](https://developer.paypal.com/docs/reports/reference/paypal-supported-currencies/)
* Other: Any currency accepted by the host. Please contact the host admin if you're unsure about whether it will be accepted

#### How do we calculate our Exchange Rate?&#x20;

* We rely on the payout provider (Wise, PayPal) whenever possible
* Otherwise we fall back on internal caching and third-party APIs, mostly [https://fixer.io](https://fixer.io/)

