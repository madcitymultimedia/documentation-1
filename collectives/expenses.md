# Expenses

## Expenses Status

The expense status is a single label that will change throughout the Expense flow and indicates what is going on with the expense.

* **Draft:** Expense is a Draft sent for someone else to complete. After 30 days, the draft will expire.
* **Unverified:** The user submitted an Expense Draft and now we're waiting for the user to verify their email in order to move it to "PENDING".
* **Pending:** Expense was submitted to the collective. We're waiting for the collective admin to approve this expense.
* **Approved:** Expense was approved by a collective admin. We're now waiting for the Fiscal Host admin to pay for it.
* **Rejected:** Collective admin rejected the expense. This is a possible final state for the Expense.
* **Scheduled for Payment:** Expense was scheduled for payment and will be paid in a batch of expenses. After being paid, the expense will be marked as "PROCESSING".
* **Processing:** Expense was paid by the Fiscal Host. We're waiting for a third-party service (Wise or PayPal) to confirm the transaction was completed.
* **Error:** Expense was paid by the Fiscal Host but something went wrong with the transaction. This is a possible final state for the Expense, the Fiscal Host will probably reach out to the User to solve any possible issue.
* **Paid:** Expense was sucessfully paid. This is the final state for the expense.
* **Spam:** This Expense was marked as SPAM and will be ignored. This is the final state for the expense.

## FAQ

### How do I know when an expense is pending?

When someone submits an [expense](../expenses-and-getting-paid/expenses.md) to your Collective, the admins will get an email notification. The email will show all the details of the expense, like who submitted it, the amount, and the receipt or invoice.

You can also view expenses on Open Collective. Click the link from the email notification, or go to your Collective page and click "View all Expenses".

![](<../.gitbook/assets/image (19).png>)

### Should I approve this expense?

The decision is up to you as a project. Some projects are informal, and any Core Contributor can approve any expense. Others have a formal decision-making or budgeting process, or only pay expenses for specific things. We advise you to have a discussion with your collaborators and agree on guidelines for approving expenses.

### Can I give guidance to expense submitters?

Yes, we recommend you have an [expense policy](collective-settings/expense-policy.md), which will show up at the top of the submit expense page.

### What happens when I click Approve?

When you approve an expense, the submitter will get a notification. The [Fiscal Host](../fiscal-hosts/fiscal-hosts.md) admin will also be notified. They review the expense and make sure it has a valid receipt or invoice, and then proceed to pay it.

### What happens when I click Reject?

The submitter will be notified that their expense was rejected. We suggest also putting a [comment](../expenses-and-getting-paid/expense-comments.md) on the expense to explain why it was rejected.

### How can I show an expense that has been paid off the platform?

Submit an expense, select manual/custom payment method, and mark it as paid. Then it will show on the budget but no money will actually move, since it’s already been paid.&#x20;

### How can I delete a pending expense?&#x20;

You will need to reject the expense and then you will be able to delete it.&#x20;
