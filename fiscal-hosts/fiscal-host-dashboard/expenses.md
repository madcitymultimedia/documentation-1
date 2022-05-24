# Expenses

![](<../../.gitbook/assets/Fiscal Host\_dashboard\_Expenses\_2022-05-24.png>)

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

* **Completed:**&#x20;
* **Refunded:** Expense has been paid and then refunded&#x20;
* **Incomplete:** Marks the expense as incomplete if there are important details missing.&#x20;

![](<../../.gitbook/assets/fiscal host\_dashboard\_incomplete2\_2022-05-24 (1).png>)

![](<../../.gitbook/assets/fiscal host\_dashboard\_incomplete\_2022-05-24.png>)

This action allows a comment to be added to the Expense activity logs and also emails the user requesting their attention.&#x20;

![](<../../.gitbook/assets/Fiscal Host\_dashboard\_markanincompletecomment\_2022-05-24.png>)

After the user edits the expense, the expense is moved back to its previous state unless the amount is also changed, which will set the expense as Pending so the collective admin can reevaluate it.

* **Ready to Pay**&#x20;

#### **Order**&#x20;

* Newest First&#x20;
* Oldest First&#x20;

#### Go to Pay

![](<../../.gitbook/assets/fiscal host\_dashboard\_gotopay\_2022-05-24 (1).png>)

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
