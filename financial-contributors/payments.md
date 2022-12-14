# Payments

## Financial contribution flow

![Screencast of the general contribution flow](../.gitbook/assets/peek-2021-01-21-17-51.gif)

## Payment options

#### Profile

Select who you'd like to pay as—yourself as an individual, or an [Organization](organizations/) or [Collective](../collectives/collectives.md) you manage.

You can also contribute anonymously by making an incognito contribution. If you chose to contribute as "incognito", your financial contribution will not show up publicly linked to your profile. However, administrators can privately see which profiles are attached to incognito contributions.&#x20;

You can find the option to donate incognito (anonymously) on the second step of the contributions page:

![](<../.gitbook/assets/Screen Shot 2021-11-17 at 11.14.35 AM.png>)

#### Payment info

1. Credit card - enter the details or use a saved card
2. [Gift card](organizations/gift-cards.md) - select the gift card you want to pay with
3. Collective - contribute [using the balance of one of your Collectives](collective-to-collective.md) (if it's in the same host as the one you're donating to)
4. [Organization](organizations/) - contribute using the balance saved to your Organization
5. Bank transfer, Paypal, or other method if made available by that Collective and their fiscal host.&#x20;

{% hint style="info" %}
**Cancelling a bank/wire/ACH transfer**\
If you don't make a bank transfer, the pending order will expire after two months and no further action is required.
{% endhint %}

## Recurring financial contributions (subscriptions)

### Why do you charge recurring monthly subscriptions on 1st of every month?

It helps Collectives manage their monthly budget and is more predictable for them. We're working on a way to charge a single payment spread out across monthly contributions, to reduce payment processor transaction fees.

### When will I be billed next time?

You will be charged when you first contribute, and then on the 1st of each month (for monthly contributions) or the 1st of the same month next year (for yearly contributions). Note: To prevent you from being charged twice in a short time frame, if you contribute after the 15th of a given month, the next charge will not be the 1st of next month but the month after.

## Contributing as a guest

If you start the contribution flow (ie. [http://opencollective.com/babel/donate](http://opencollective.com/babel/donate)) while being logged out, the system will allow you to continue without signing in/up, just by providing your email address. Note that guest accounts are not automatically anonymous- you need to not put your name in under "Full Name," i.e. write "guest" or "anonymous," otherwise it will show up along with the transaction. For information about submitting a contribution anonymously (incognito) if you already have an Open Collective profile, [see above](https://docs.opencollective.com/help/financial-contributors/payments#profile).&#x20;

{% hint style="info" %}
Above a certain amount, the system will ask you additional information such as your physical address. This information is required for legal purpose, and stays private.
{% endhint %}

{% hint style="warning" %}
Guest contributions are not yet supported for recurring contributions or in case the email that you're trying to use is already a verified account on Open Collective. We are currently working on removing these limitations.
{% endhint %}

![Guest contribution form](<../.gitbook/assets/image (5) (1).png>)

### Claiming a Guest Account

There are two ways to claim a guest account:

#### 1. By clicking on "Join Open Collective" on the success page

![](<../.gitbook/assets/image (37).png>)

You'll then get an email to register on Open Collective. Click on the given link and your account will be verified!

![](<../.gitbook/assets/image (21).png>)

#### 2. By signing in

Sign in directly by clicking on the "Sign in" button in the top navbar will have the same effect of verifying your account directly.

## Payment changes

To view your current payment methods, go to your profile (under 'my account') and click 'edit profile', then 'payment methods'.

### Change the amount, payment method or cancel an existing contribution

Make sure you are logged in and then click on your profile in the top right hand corner&#x20;

<figure><img src="../.gitbook/assets/financialcontributor_payments_cancel_2022-09-14 (1).png" alt=""><figcaption></figcaption></figure>

This should open the dropdown menu next to your profile avatar. Click on **Manage Contributions.**

![](<../.gitbook/assets/image (31).png>)

You'll be redirected to a page with all of your recurring financial contributions. Click on the edit button at the bottom of the financial contribution card to update your payment method, amount or cancel.

![From there you can see all your recurring contributions](<../.gitbook/assets/image (11).png>)

![Click on "Edit" do see the options](<../.gitbook/assets/image (15) (1).png>)

### How to add, change or remove payment method

1. Click on your user profile in the top right-hand corner
2. Click on settings&#x20;

![](<../.gitbook/assets/financialcontributors\_payments\_removepaymentmethod\_2022-08-11 (1).png>)

3\. To remove: Click on Payment methods - If your card has active recurring contributions, you'll need to cancel them before you can remove your payment method.\
\
To add a credit card: Click on add a credit card at the bottom.&#x20;

_**Note:** Adding a new card does not change the card for existing recurring contributions._

![](../.gitbook/assets/financialcontributors\_payments\_removecontributions\_2022-08-11.png)

4\. Otherwise, just click "Remove" then "Ok"

![](../.gitbook/assets/financialcontributors\_payments\_remove\_2022-08-11.png)

### Refunds&#x20;

Refunds are approved and processed by the fiscal hosts subject to their terms and conditions. Please [contact](https://opencollective.com/contact) our team with details about your refund request, the amount, the date the transaction occurred and a link to the collective and we will pass your query along to the right fiscal host.&#x20;

Open Source Collective [Refund Policy](https://docs.oscollective.org/faq/expenses#how-can-i-get-a-refund-on-a-payment-or-donation)&#x20;

## Credit Card Verification

To comply with banking regulations, we may have to ask financial contributors to verify their credit cards. This mainly occurs in Europe but is being deployed across more countries. In Europe, the policy is named [Strong Customer Authentication](https://en.wikipedia.org/wiki/Strong\_customer\_authentication). 3D Secure is the most common way of authenticating an online card payment, which asks you to confirm the payment through your phone, banking app, or dedicated device.

While processing recurring contributions, contributors whose credit cards need confirmation will receive an email looking like this:

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>"Verify your credit card" email</p></figcaption></figure>

Click on the "Verify my credit card" button, then you'll be redirected to https://opencollective.com where you may have to sign in with your email address if you're not already. Finally, a prompt with the confirmation page of your bank will appear (the way it will look will depend on your bank):

_Screenshot to be added_

### FAQ

*   **What will happen if I don't verify my credit card?**

    If you don't verify your credit card, we will not be able to process your recurring payment. We will retry in the coming days, then after 6 attempts, your recurring contribution will be cancelled.
* **Why does it fail when I try to verify my credit card?**\
  ****Make sure you turn extensions such as ad blockers off and that your browser is up-to-date. Some errors can also originate from the bank verification services not working correctly. If everything else fails, feel free to [contact us](https://opencollective.com/contact).
