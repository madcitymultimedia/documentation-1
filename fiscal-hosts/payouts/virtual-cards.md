# Virtual Card Settings

{% hint style="warning" %}
**This feature is currently in a closed Beta test.**
{% endhint %}

Virtual cards can be offered to collectives through Hosts. Hosts create virtual cards using our provider [Stripe.com](https://www.stripe.com) and assign them to a Collective. Anyone with access to that card can then use it to make payments on behalf of the Collective. When a payment is made an expense is automatically created for the Collective and the owner is notified to attach a receipt. Virtual Cards are particularly useful for recurring payments like hosting a website.

## Connecting to Stripe

* Get the API Key from your Privacy.com account:
  * Open a new tab and go to your [Privacy account settings](https://privacy.com/account).
  * Click on "Enable API".
  * Select "Production" environment.
  * Enable Production Webhook and set the address to: `https://api.opencollective.com/webhooks/privacy`
  * Copy your Production API Key for the next step.

![](../../.gitbook/assets/screenshot-from-2021-08-03-15-56-54.png)

* Add your API key to your Collective settings:
  * Open your Collective settings and open the "Sending Money" page.
  * Paste your API Key in the "API Key" field and click on "Connect Privacy".

![](../../.gitbook/assets/screenshot-from-2021-08-03-16-04-49.png)

## Accessing Virtual Card Settings

To access your virtual card settings and policy, go to your host's admin panel and open select 'Virtual Cards Settings' under your Fiscal Host Settings section:

![You can find the Virtual Card Settings menu under Fiscal Host Settings in your Fiscal Host admin panel.](<../../.gitbook/assets/image (50) (1).png>)

### Enable card requests

It is possible to create and assign virtual cards to Collectives without enabling users to request them.&#x20;

Toggle the 'allow collectives to request a card' option to allow Collectives to request a card. Collectives can request a Virtual Card by clicking _**Request a card**_ from their profile page:

![You can request a card from your collective's Actions menu.](<../../.gitbook/assets/image (52) (1).png>)

### Automatically notify collectives about pending receipts

You can toggle this option to automatically send a reminder for charge expenses that were created but are still missing their receipts. These reminders are sent after 15 and 29 days the expense was created.

### Automatically suspend cards

You can toggle this option if you want to automatically pause _**Stripe issued virtual cards**_ after any of its charge expenses is 31 days missing its receipt. This will also automatically resume paused cards after all missing expenses are submitted.

### Setting a policy

Hosts have complete control over when, how, and to who they provide Virtual Cards. Hosts can define their own policy in the 'Virtual Card Policy Information' area.

## Creating and assigning cards

Virtual Cards are created using our provider [Stripe](https://www.stripe.com). To create a card on [Stripe](https://www.stripe.com) register and follow the details [here](https://stripe.com/en-gb-fr/issuing).

Once you have created a card on [Stripe ](https://stripe.com/en-gb-fr)you can assign it to a Collective:

![Assigning a Virtual Card](../../.gitbook/assets/screenshot-2021-05-12-at-12.54.06.png)

Select a Collective then select a user who is responsible for this card. This user will be automatically added to expenses created when a purchase is made using this card and they will be notified and asked to provide a receipt.

Click 'Save Card' to save the card to the Collective.

## Viewing Card details

You can view all cards assigned to Collectives from the Virtual Cards settings page. Here you can filter cards by status, merchant, and Collective.

![Filter virtual cards by status, merchant or collective.](../../.gitbook/assets/screenshot-2021-05-12-at-16.11.02.png)

Each card shows the name, status, assigned collective, when the card was assigned and any limits set on the card in Stripe. The last four digits of the card are also shown. To view the full details of a card click 'view card details'.

{% hint style="warning" %}
Be aware of your surroundings when viewing a card's details as others may be able to see them.
{% endhint %}

## Changing virtual card spending limits, owners and collectives

Virtual Card spending limits can be modified using Stripe. We do not provide facilities for moving cards between Users or Collectives. This ensures that we have clear records for Collectives with clear responsibilities. If you need to re-assign a card, delete the card then create and assign a new one instead.

If you need to make a change to the initiative's card, please update it to the correct amount in Stripe, and then [contact us](https://opencollective.com/contact) with a screenshot so that our team can make the adjustment on the platform.

## Pausing, resuming, and deleting a card

Pausing, resuming, and deleting should be done through Stripe's dashboard. Don't worry about syncing the information to the platform, our work will take care of updating the card state or deleting the cards that were removed from your Stripe account every hour.

### Virtual Cards Charge Expense Explanation

Unlike our previous integration with [Privacy.com](http://privacy.com/), Stripe supports authorization tripe validation, which means we can do internal validations at the time the user pays for something using their card.

\
Currently, we use this feature to validate that the collective using its card, has enough balance to cover the purchase they're trying to make. If they don't have enough balance the payment will fail and, if they have balance, we'll instantly create the charge expense in their collective.

\
Since there's a delay between the authorization of purchase and the actual charge, we keep this expense in "PROCESSING" status until the purchase is actually charged.\
During this period, the user can already attach a receipt to the expense, but they should bear in mind that the amount may change between the authorization and the actual charge.

\
If the authorization is cancelled before there's an actual charge, we simply delete the expense.\


After the charge is received, this expense is then moved to the "PAID" status and we create the necessary transactions in the collective ledger using the final charged amount.

\
After this point, if the purchase is refunded, we'll create a new pair of transactions to credit the amount back to the collective and the charge expense will be set to "CANCELED".&#x20;
