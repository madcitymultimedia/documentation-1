# Contribution flow

The contribution flow is how users support a collective on Open Collective. The Contribution flow can be directly accessed via this link: e.g. [https://opencollective.com/webpack/donate](https://opencollective.com/webpack/donate)

Replace 'webpack' with your collective slug to generate your own.&#x20;

## Custom contribution amounts

The contribution flow supports many URL parameters to pre-fill the contribution.

Example: [https://opencollective.com/webpack/donate?amount=66.66\&platformContribution=3.34\&interval=month\&skipStepDetails=true](https://opencollective.com/webpack/donate?amount=66.66\&platformContribution=3.34\&interval=month\&skipStepDetails=true).&#x20;

This link will bring you directly to the profile step of the contribution flow for webpack, with a monthly contribution of $66.66 + $3.34 tip.



| Parameter                    | Type                          | Description                                                                                                                                                                      | Example                                          |
| ---------------------------- | ----------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| `amount`                     | Float number                  | Contribution amount                                                                                                                                                              | `amount=42.42`                                   |
| `platformContribution`       | Float number                  | Platform tip amount                                                                                                                                                              | `platformContribution=5.5`                       |
| `quantity`                   | Integer                       | Number of units (for tickets/products)                                                                                                                                           | `quantity=5`                                     |
| `interval`                   | `month`, `year`               | Contribution interval                                                                                                                                                            | `interval=month`                                 |
| `skipStepDetails`            | `true`, `false`               | Whether to skip the 1st step (default: false)                                                                                                                                    | `skipStepDetails=true`                           |
| `contributeAs`               | string                        | slug of the default profile to use of the contribution                                                                                                                           | `contributeAs=facebook`                          |
| `disabledPaymentMethodTypes` | string list (comma separated) | See [this list](https://github.com/opencollective/opencollective-frontend/blob/3ce48b82097087860d35e6b896d3bd04568af599/lib/constants/payment-methods.js#L8) for accepted values | `disabledPaymentMethodTypes=CREDITCARD,GIFTCARD` |

## Embed Contribution flow&#x20;

To integrate a "Contribute" option directly on your website

{% hint style="warning" %}
This feature is currently in a beta-test phase. If you face any issue or need assistance, you can send a message on [Slack](https://slack.opencollective.com) (#﻿embed-contribution-flow channel)
{% endhint %}

The embed contribution flow is a way to integrate Open Collective on your own website. Visitors will be able to contribute directly, by simply providing an email address.

![Embedded contribution on the website of an initiative](<../.gitbook/assets/image (4).png>)

### General considerations

* The widget will look better if it has some space, ideally the full page height & width
* The following URL parameters can be used to configure your integration:

| Parameter                    | Value type | Default value | Description                                                                                                                                                                                                                                   |
| ---------------------------- | ---------- | ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `useTheme`                   | Boolean    | true          | <p></p><p>By default, the theme of your profile (defined by your primary color) will be used. If you rather want to use the default Open Collective theme, set this to <code>false</code>.</p>                                                |
| `hideHeader`                 | Boolean    | false         | Set this to `true` to hide the header at the top                                                                                                                                                                                              |
| `disabedlPaymentMethodTypes` | \[String]  | null          | A list of payment method types to disable. Example: `[CREDITCARD, MANUAL, CRYPTO]`                                                                                                                                                            |
| `tags`                       | \[String]  | null          | <p>Some tags to attach to the orders. If you're embedding the contribution flow on multiple pages/websites, you can use this to track from where the contributions are coming from.</p><p>Max number of tags: 30</p><p>Max tag length: 32</p> |

### Embed the default tier (Donate)

The simplest way to embed the contribution flow is by using the `/donate` URL (e.g. [https://opencollective.com/babel/donate](https://opencollective.com/babel/donate)). Just replace `COLLECTIVE_SLUG` by your collective slug below:

```markup
<iframe src="https://opencollective.com/embed/COLLECTIVE_SLUG/donate" style="width: 100%; min-height: 100vh;"></iframe>
```

### Embed a specific tier

To embed a specific tier, you'll need to know its ID. For that, go to your profile page, click on "Contribute" for the tier you want to embed then check the URL. It should look like `https://opencollective.com/COLLECTIVE_SLUG/contribute/TIER_SLUG-TIER_ID/checkout`

From this URL, you can deduct the embedded one (prefix with `embed` and removes `/checkout`):

```markup
<iframe src="https://opencollective.com/embed/COLLECTIVE_SLUG/contribute/TIER_SLUG-TIER_ID" style="width: 100%; min-height: 100vh;"></iframe>
```

### Embed an event ticket

Embedding for event tickets uses the same route as regular tiers. you must make sure to remove the parent collective path and to include a slug. The slug can be anything, so if you're not sure feel free to put any value in there. For example, this path:

> [https://opencollective.com/mautic/events/mautic-conference-europe-4da0de72/order/32898](https://opencollective.com/mautic/events/mautic-conference-europe-4da0de72/order/32898)

can be embedded as:

> [https://opencollective.com/embed/mautic-conference-europe-4da0de72/contribute/general-access-ticket-32898](https://opencollective.com/embed/mautic-conference-europe-4da0de72/contribute/general-access-ticket-32898.)
