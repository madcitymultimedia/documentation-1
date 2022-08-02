---
description: How to setup Virtual Cards in local development
---

# Virtual Cards

{% hint style="warning" %}
This documentation is about development. To setup a production environment, see [https://docs.opencollective.com/help/fiscal-hosts/virtual-cards](https://docs.opencollective.com/help/fiscal-hosts/virtual-cards)
{% endhint %}

## Setup Stripe in development

{% hint style="info" %}
On staging, [https://staging.opencollective.com/opensource/](https://staging.opencollective.com/opensource/) is already configured to issue virtual cards. If what you're working on doesn't require any API changes, feeel free to use it directly.
{% endhint %}

The steps to configure Stripe issuing on your local setup are:

1. Ask Stripe to enable Issuing on your account https://dashboard.stripe.com/setup/issuing/activate (if you're managing multiple accounts, make sure to pick the right account on top)
2. Top Up the Issuing balance with a reasonable amount ($1000 ?, $10,000 ?)
3. Create a generic Card Holder and make sure it's the only one (if you have more, let us know)
4. Configure webhook and enable for all `issuing_authorization.*` and `issuing_transaction.*` (5 events) `https://api.opencollective.com/webhook/stripe`
5. Configure default authorization process and webhook (deny or allow) (Optional) https://dashboard.stripe.com/settings/issuing/authorizations
6. Create new dedicated Restricted Secret Key, select `write` for all Issuing features (Name: Restricted Issuing)
7. Contact Open Collective Engineering team to configure Restricted Secret Key production (update-connected-account-stripe-token)
8. Contact Open Collective Engineering team to configure Webhook Signing secret to connected account (stripeEndpointSecret)
9. Ask Open Collective Engineering team to enable feature in Collective settings (privacyVcc)

## Setup privacy in development

{% hint style="warning" %}
Privacy is deprecated and shouldn't be used for new developments
{% endhint %}

1. Create an account on [https://privacy.com](https://privacy.com/)
2. Go to [https://privacy.com/account](https://privacy.com/account), scroll down to "Enable API", toggle the switch, click on Sandbox and copy the Sandbox API key (**NOT THE PRODUCTION ONE**)

![](<../../.gitbook/assets/image (16) (2).png>)

3\. Connect to the database with your favorite tool (psql, DBeaver, Postico, etc.) and search for the host you want to enable Privacy for. Edit its `settings` to set `features.privacyVcc` to `true`

4\. Open the host settings and go to the "Fiscal host settings" > "Sending Money" section

5\. Paste your API Key in the "API Key" field and click on "Connect Privacy".
