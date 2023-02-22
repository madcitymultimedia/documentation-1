# Virtual Card Settings

Virtual cards can be offered to collectives through Hosts. Hosts authorise and create virtual cards, assigning them to a Collective administrator. Anyone with access to that card can then use it to make payments on behalf of the Collective. When a payment is made, an expense is automatically created for the Collective; the owner is then notified to attach a receipt.&#x20;

{% hint style="info" %}
Virtual Cards are particularly useful for recurring payments like hosting a website.
{% endhint %}

Virtual Cards created using Open Collective will authorise transactions against the Collective's balance in real-time. Cards additionally be configures with a number of spending controls to de-risk abuse.&#x20;

## Connecting to Stripe

Open Collective uses Stripe Issuing to manage virtual cards. We have extended support for Stripe that enables hosts to create, edit, pause, resume and cancel cards, including the option to automatically pause and resume cards with missing receipts.&#x20;

{% embed url="https://support.stripe.com/questions/getting-started-with-issuing" %}

1. Go to the above page, contact the Issuing sales team to get set up with Stripe Virtual Cards.&#x20;
2. Ensure [Stripe is connected](../receiving-money/credit-card.md) to your account.&#x20;

### Adding an Issuing balance&#x20;

Stripe Issuing uses an Issuing Balance that is separate from currency balances held within Stripe. Virtual Cards use this balance when processing transactions. Be sure to add to your issuing balance regularly.&#x20;

## Accessing Virtual Card Settings

To access your virtual card settings and policy, go to your host's admin panel and open select 'Virtual Cards Settings' under your Fiscal Host Settings section:

![You can find the Virtual Card Settings menu under Fiscal Host Settings in your Fiscal Host admin panel.](<../../.gitbook/assets/image (50) (1).png>)

### Enable card requests

It is possible to create and assign virtual cards to Collectives without enabling users to request them.&#x20;

Toggle the 'allow collectives to request a card' option to allow Collectives to request a card. Collectives can request a Virtual Card by clicking _**Request a card**_ from their profile page:

![You can request a card from your collective's Actions menu.](<../../.gitbook/assets/image (52) (1).png>)

Hosts are notified of virtual card requests by email.&#x20;

### Automatically notify collectives about pending receipts

You can toggle this option to automatically send a reminder for charge expenses that were created but are still missing their receipts. These reminders are sent after 15 and 29 days the expense was created.

### Setting a policy

Hosts have complete control over when, how, and to who they provide Virtual Cards. Hosts can define their own policy in the 'Virtual Card Policy Information' area.&#x20;

{% hint style="success" %}
Virtual card policies are provided to users when requesting a card. They can contain a binding agreement if needed.
{% endhint %}

## Viewing Card details

You can view all cards assigned to Collectives from the Virtual Cards settings page. Here you can filter cards by Collective:

<figure><img src="../../.gitbook/assets/Screenshot 2022-12-22 at 11.54.23.png" alt=""><figcaption></figcaption></figure>

Each card shows the name, status, assigned collective, when the card was assigned and any limits set. The last four digits of the card are also shown. To view the full details of a card click 'view card details'.

{% hint style="warning" %}
Be aware of your surroundings when viewing a card's details as others may be able to see them.
{% endhint %}

### Creating cards

Cards can be created from within Open Collective with Stripe Issuing. [Read more about Stripe Issuing](virtual-cards.md#connecting-to-stripe).   \
\
Once connected, cards can be created from your Host Settings (Select 'Virtual cards' and 'create card') or from the 'actions' panel on a hosted collective's profile page:

<figure><img src="../../.gitbook/assets/Screenshot 2022-12-22 at 11.09.14.png" alt=""><figcaption><p>creating a card from a Collective's profile page.</p></figcaption></figure>

Select the Collective to assign the card to (this is automatically filled if creating from a Collective's profile page), the assignee, a name for the card and limit:

<figure><img src="../../.gitbook/assets/Screenshot 2022-12-22 at 11.11.13 (1).png" alt=""><figcaption><p>Creating a virtual card.<br></p></figcaption></figure>

### Card Limits

Virtual Cards issued with Stripe can be limited on a daily, weekly, monthly or yearly basis. They can also be limited on a per-transaction basis or assigned a total spending limit (all time). [Read more about Stripe's spending controls](https://stripe.com/docs/issuing/controls/spending-controls?locale=en-GB).

### Automatically suspending cards

Hosts can toggle this option from the [Virtual Card Settings](virtual-cards.md) if they wish to automatically pause virtual cards after an expense is missing its receipt after 31 days. Cards will resume once all missing expenses are submitted.

### Changing virtual card spending limits, owners and collectives

Cards issued with Stripe Issuing's details, including 'assignee', name, and spending limits can be edited from the [Virtual Card View](virtual-cards.md#viewing-card-details).  It is not possible to re-assign a virtual card to another Collective.&#x20;

### Pausing, resuming, and deleting a card

Cards issued using Stripe Issuing can also be paused, resumed and cancelled from the [Virtual Card View](virtual-cards.md#viewing-card-details). Cards paused, resumed and cancelled directly through Stripe will be synchronised. \


## Troubleshooting Virtual Card Transactions

Card transactions appear in the assigned Collective's expenses.&#x20;

Expenses that are authorized will debit the collective's balance and appear as `PROCESSING`  until the card is charged, at which time the expense will be marked as`PAID`. Assignees are able to upload a receipt to expenses that are still processing.&#x20;

\
If the authorization is cancelled before there's an actual charge, we simply delete the expense.\
\
If the purchase is refunded, a new refund transaction to be added to credit the amount back to the collective and the charge expense will be set to "CANCELED".
