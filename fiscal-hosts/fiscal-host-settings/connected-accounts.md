---
description: >-
  You can connect social media accounts to automatically thank new financial
  contributors
---

# Connect external accounts

## Connecting a Twitter account

Click on **Connect Twitter**. You will be prompted to either directly authorize Open Collective to access your account or to log in and authorize it.

Connecting your account will provide you a few automation options based on how many financial contributors Collectives you host have reached:

![Options for activating automated tweets whenever a Collective you host reach 10, 100 and 1,000 financial contributors.](../../.gitbook/assets/fiscal-host\_fiscal-host-settings\_settings-connected-accounts-settings\_2020-07-13.png)

To use a template parameter, put it in brackets like this: `{collective}`. Here are the parameters supported by each template:

| Parameter                  | Templates                                                                     | Description                                                                    | Example                                                                                                                                    |
| -------------------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `backerTwitterHandle`      | New financial contributors                                                    | Twitter Handle of the contributor without the `@` prefix (can be empty)        | `myUsername`                                                                                                                               |
| `amount`                   | New financial contributors                                                    | Contribution amount with the currency                                          | `$10.00`                                                                                                                                   |
| `collective`               | <p>Ten contributors<br>Fifty contributors<br>One hundred contributors<br></p> | Either the collective name or, if set, the Twitter handle prefixed with an `@` | `@babel`                                                                                                                                   |
| `topBackersTwitterHandles` | Ten contributors                                                              | Top 10 contributors names or handles                                           | Facebook, @airbnb, company3, joe, @anotherAccount, anotherAccount2, anotherAccount3, anotherAccount4, anotherAccount5, anotherAccount6, +6 |

## Receiving contributions through PayPal

{% hint style="info" %}
This feature is currently in **beta**, meaning it's still being tested. To turn on PayPal contributions, [email support](mailto:support@opencollective.com).
{% endhint %}

### Fees

Payment processor fees charged by PayPal will be automatically deducted. If any platform tips or platform share is paid through PayPal, it will go to your account and will be paid later, via the monthly settlement expense.

### Connecting PayPal

If you're already in the beta test group, you can follow these instructions:

*   [ ] Create a new PayPal app

    * Open [PayPal's Developer](https://developer.paypal.com/developer/applications/) page and Log In.
    * In _My Apps & Credentials_ page, select the **Live** environment, and click in _Create app_.

    ![](<../../.gitbook/assets/image (25).png>)

    * Name this App after Open Collective, this way you'll always remember where this token is being used.
    * Click _Create App._

![](../../.gitbook/assets/screen-record-from-2020-07-10-13.30.21.gif)

* [ ] Then scroll down to "Live App Settings" and make sure "**Accept payments"** and **"Payouts"** are checked

![](<../../.gitbook/assets/image (13).png>)

* [ ] Now, copy the necessary information to Open Collective.
  * Open a new tab and go to [Open Collective](https://www.opencollective.com).
  * Open your Host collective settings page and click in the _Receiving Money_ option in the menu.
  * Copy and paste _Client ID, Secret_ in the respective fields, leave Webhook ID empty.
  * Click _Connect PayPal._
