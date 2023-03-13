# Expenses

### **Filter**&#x20;

#### **Type**&#x20;

* All expenses&#x20;
* Charge&#x20;
* Invoice&#x20;
* Receipt&#x20;
* Grant&#x20;
* Settlement&#x20;
* Unclassified&#x20;

#### **Payout**&#x20;

* All methods&#x20;
* Open Collective&#x20;
* Bank Transfer&#x20;
* PayPal&#x20;
* Virtual Card&#x20;
* Other&#x20;

#### Period&#x20;

* All time&#x20;
* Today&#x20;
* This Month&#x20;
* Past Week&#x20;
* Past Month&#x20;
* Past Year&#x20;

Custom Date selection&#x20;

* Timezone - Local or UTC - By default, all dates are filtered and displayed using your local timezone. You can switch to UTC to indicate that the dates provided above use the Coordinated Universal Time format, which matches how email reports are generated.&#x20;
* Start Date&#x20;
* End Date&#x20;

#### Amount&#x20;

* All&#x20;
* $0 - $50&#x20;
* $50 - $500
* $500 - $5,000
* $5,000 and above&#x20;

#### Status&#x20;

* **Pending:** **** Expense was submitted to the collective. We're waiting for the collective admin to approve this expense.

![](<../../.gitbook/assets/fiscal host\_dashboard\_pending\_2022-05-24.png>)

* **Approved:** Expense was approved by a collective admin. We're now waiting for the Fiscal Host admin to pay for it.

![](<../../.gitbook/assets/fiscal host\_dashboard\_approved\_2022-05-24 (1).png>)

* **Rejected:** Collective admin rejected the expense. This is a possible final state for the Expense.

![](<../../.gitbook/assets/fiscal host\_dashboard\_rejected\_2022-05-24.png>)

* **Processing:** Expense was paid by the Fiscal Host. We're waiting for a third-party service (Wise or PayPal) to confirm the transaction was completed.

![](<../../.gitbook/assets/fiscal host\_dashboard\_processing\_2022-05-24.png>)

* **Error:** Expense was paid by the Fiscal Host but something went wrong with the transaction. This is a possible final state for the Expense, the Fiscal Host will probably reach out to the User to solve any possible issue.

![](<../../.gitbook/assets/fiscal host\_dashboard\_error\_2022-05.png>)

* **Paid:** Expense was sucessfully paid. This is the final state for the expense.

![](<../../.gitbook/assets/fiscal host\_dashboard\_paid\_2022-05-24.png>)

* **SPAM:** This Expense was marked as SPAM and will be ignored. This is the final state for the expense

![](<../../.gitbook/assets/fiscal host\_dashboard\_spam\_2022-05.png>)



* **Incomplete:** Marks the expense as incomplete if there are important details missing to complete the payment. Only Approved/Error expenses can be marked as incomplete.

![](<../../.gitbook/assets/fiscal host\_dashboard\_incomplete2\_2022-05-24 (1).png>)

![](<../../.gitbook/assets/fiscal host\_dashboard\_incomplete\_2022-05-24 (1).png>)

This action allows a comment to be added to the Expense activity logs and also emails the user requesting their attention.&#x20;

![](<../../.gitbook/assets/Fiscal Host\_dashboard\_markanincompletecomment\_2022-05-24.png>)

After the user edits the expense, the expense is moved back to its previous state unless the amount is also changed, which will set the expense as Pending so the collective admin can reevaluate it.

* **Ready to Pay -** Reference the [Go to Pay](expenses.md#go-to-pay) section below.&#x20;

#### **Order**&#x20;

* Newest First&#x20;
* Oldest First&#x20;

## Paying Expenses

### Security Checks

{% hint style="info" %}
This is the first batch of security checks we have implemented. They were created based on past cases we had on the platform, and we plan to keep iterating on these checks with the input of fiscal hosts. You can contribute with feedback here: [https://:.com/opencollective/opencollective/issues/6097](https://github.com/opencollective/opencollective/issues/6097)
{% endhint %}

We're adding warnings about payees to protect Collectives and Hosts from fraudulent expense claims.

These warnings are designed to inform you as to whether you should approve or pay an expense. They are not a part of an enforcible policy within Open Collective but we encourage hosts and Collectives to consider creating and documenting policies as part of their terms or code of conducts if needed.

<figure><img src="../../.gitbook/assets/image (4) (2).png" alt=""><figcaption><p>You'll find the Security Checks with other expense processing buttons.</p></figcaption></figure>

You can review the Security Checks by clicking the shield button. This button varies in color following the highest risk level we found in the expense. In the case the expense poses a high-security level, we're also presenting this information as a necessary confirmation before you go to the Pay modal.

<figure><img src="../../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption><p>The Security Checks modal.</p></figcaption></figure>

The security checks are categorized in scope and risk level. The categories are:

* **User:** The user who submitted the expense, the author of the expense or draft sent as an invite to submit the expense.
* **Payee:** If the beneficiary is not the user who originally submitted the expense, we also list checks on that profile through the _Payee_ scope.
* **Payout Method:** The actual beneficiary information that is going to be paid by the expense.

The risk levels are:

* <mark style="color:green;">**PASS**</mark>: Opposite of a security risk, actually indicates good record or behavior.
* <mark style="color:blue;">**INFO/LOW**</mark>: Contextual information for transparency sake, these are informations that may be important on a particular context but are not meaningful by themselves.
* <mark style="color:yellow;">**MEDIUM**</mark>: Important to consider, may require some investigation given the context.
* <mark style="color:red;">**HIGH**</mark>: Represents a risk or complete lack of information and requires investigation. This behavior was previously related to fraud.

It is important to understand that these checks are evaluated independently, and it is up to the host admin to evaluate the whole context and take their decision. The security checks currently implemented are listed below, but keep in mind that we'll keep working on adding new check routines and adjusting their existing levels. Some of the existing security checks include:

* User impersonation checks based on IP correlation and Connected Accounts username overlaps.
* User 2FA status conveys the security risk of the author account itself.
* User role in the Collective and/or Fiscal Host exposing how the user relates to the collective or fiscal host.
* Past user behaviour based on expenses rejected or marked as spam.
* Past expenses that have been submitted on the platform and in the same collective.
* Bank account information and PayPal email correlation between users and collectives.

### Go to Pay

![](<../../.gitbook/assets/fiscal host\_dashboard\_gotopay\_2022-05-24.png>)

Green button showing that an expense has been approved and there are sufficient funds. If you click this button, the pay expense modal will be displayed and you'll be able to pay for the expense using a suitable method.

![Pay Expense modal displayed for an expense submitted with Bank Account on a Host connected to Wise.](../../.gitbook/assets/screenshot-from-2021-06-29-16-11-03.png)

The action button displayed in this modal will vary with the available integration the host have and the payout method selected by the user who submitted the expense.

In the case you're paying with PayPal, if you click the action button the expense will automatically be paid from the connected PayPal account. If you're using PayPal Payouts, the expense will be marked as Scheduled for Payment and automatically processed by the payment worker.

In the case you're paying with Wise, if you click the action button the expense will automatically be paid from your main Wise balance. If your Wise requires OTP authorization, the expense will be Scheduled for Payment and a banner will be displayed on top of your expenses list so you can pay all the scheduled expenses in a batch with a single validation.

![Scheduled Wise expenses are paid manually in batch with your account requires OTP authorization.](../../.gitbook/assets/screenshot-from-2021-06-29-16-18-33.png)

#### Mark as Paid

Green button for manual payments. After paying via another method (bank transfer, etc), click this to deduct the amount for the Collective's budget in the system.

#### Edit

Host admins have permission to edit expenses at any time. For example, someone wasn't able to attach their receipt and emailed it instead, and you are adding it for them.

**Note:** If you edit an expense, it must be re-approved.

#### Open Expense

If you click the title of an individual expense, you will go to that expense's page. There, you can see all details and read or add [comments](../../expenses-and-getting-paid/expense-comments.md).

#### Connect PayPal & refill balance

PayPal allows you to pre-approve $2,000 at a time to be paid through the API. This is a security feature. This means after you've paid out $2,000 in expenses, you need to refill the balance. If you try to pay an expense and get an error about the PayPal balance, it's time to refill.

When you click "refill balance" you will be prompted to log in to PayPal, and afterwards you'll be taken back to your dashboard.

You can see the connected PayPal account in the top right. This is the account expenses will be paid out of.

If you manage multiple PayPal accounts, make sure it's the right one! If it's not correct, open PayPal in another tab and manually log out, then click "refill balance" and use credentials for the right account.

#### Payment Error Troubleshooting

Payment errors will show in red next to the expense if they come up.

Common reasons for a payment to fail after clicking the "Pay with PayPal" button:

* Need to refill the pre-approval balance
  * Click the 'refill balance' button
* Insufficient funds to cover fees
  * There are not enough funds in the Collective to pay this expense. Many Collectives submit expenses in anticipation of future funding.
  * If a user submits an expense for 100% of the Collective's balance, there won't be enough to cover processing fees
  * Edit the expense total down to leave enough for the fees and inform the user by leaving a comment
* User's PayPal account is restricted
  * Ask the user to log into PayPal and resolve the issue on their side

### Multi-Currency Expenses&#x20;

Here is an example of how a Multi-Currency expense will show in the expense list. The amount will show in the expense currency, with the amount converted into the host currency below.&#x20;

![](../../.gitbook/assets/fiscalhosts\_dashboard\_expenses\_multi\_9-8-2022.png)

The same will show in the pay expenses modal. Example below.&#x20;

![](../../.gitbook/assets/fiscalhosts\_dashboard\_expenses\_9-8-2022.png)
