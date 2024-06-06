---
description: Information and instructions for setting up and using 2FA for payouts.
---

# Two-factor authentication for payouts

{% hint style="danger" %}
With the implementation of the new [Dashboard interface](https://docs.opencollective.com/help/product/understanding-your-dashboard), we are currently in the process of updating our documentation and some pages may be out of date. Thank you for your patience. Please [contact](https://opencollective.com/contact) our support team if you need any assistance.
{% endhint %}

Fiscal hosts now have the ability to enable two-factor authentication on payouts. This means that when you go to the host dashboard and click “Go to pay” to open the payment modal, you will sometimes be prompted to enter a 2FA code as an extra layer of security.

## Enabling 2FA for login

First, you need to enable two-factor authentication on your user account. You can find the instructions on how to do this [here](../../product/two-factor-authentication.md).&#x20;

## Enabling 2FA for payouts

Now you’re ready to make payouts from the host dashboard. Click “Go to pay” for the first expense.

![](../../.gitbook/assets/FiscalHosts\_Payouts\_Twofactor\_2021-07-5.png)

The payment modal will then open, giving you the option to pay out for the expense.

![](../../.gitbook/assets/FiscalHosts\_Payouts\_Twofactor\_Payexpense\_2021-07-5.png)

For the first expense that you’re paying in a “session”, you will be prompted to enter your 2FA code. Open your authenticator app and enter the 6-digit code that is under the entry for your account on Open Collective.&#x20;

![If you use Google Authenticator, this is what an entry for Open Collective might look like.](<../../.gitbook/assets/Screenshot 2020-11-20 at 12.58.01.png>)

Then click the pay button in the modal again. If the code is correct, then the payment should go through.

What happens now that you have “authenticated” by putting in your 2FA code is that you are allowed to make any number of payments until the sum of their amounts add up to a limit (which defaults to $10,000.00). When the sum of the amounts of all the payments you’ve made goes over the limit, you are then asked to enter your 2FA code again in order to keep making payments.

If you and another admin/accountant for your organization are making payments at the same time, you each get your own limit instead of working against a shared one.

{% hint style="warning" %}
When you enable 2FA for payouts on your organization, every admin or accountant who makes payments will need to enable 2FA for login on their individual accounts, so please make sure to let them know this before enabling it.
{% endhint %}
