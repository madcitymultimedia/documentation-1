---
description: >-
  Procedure and documentation about how to contribute to the Open Collective
  translations
---

# Translation

{% hint style="info" %}
We use Crowdin to manage all our translations. You can join and contribute on: [https://translate.opencollective.com/](https://translate.opencollective.com/)
{% endhint %}

Quick tour

{% embed url="https://www.loom.com/share/467aeead7ed74128935a2b1e03bc9220" %}

## Adding a new language

To ask for a language to be added on Crowdin, feel free to [open a discussion](https://crowdin.com/project/opencollective/discussions). We always accept these requests, but please note that inactive languages will often be removed if there's no contribution.

## Format

### Variables

Words between brackets are variables that meant to be replaced by dynamic values.

For example the string:

```
Hello {collectiveName}!
```

Will render as **`Hello Webpack!`** if the collective name is Webpack. You must never change the variable names.

### Select

`select` is a special command that lets us render different texts conditionally. The base pattern is:

```
{myVariable, select, value1 {Rendered if myVariable=value1} other {Otherwise this}}
```

A classic example for that is the interval select:

```
{amount} {interval, select, month {monthly} year {yearly}}
```

Here `interval` is the variable with `month` and `year` as possible values. If amount is equal to `$5` and interval to `year`, the template above will be rendered to:

```
$5 yearly
```

Here again, don't change the variable name or the `select` keyword, only the replaced strings (`monthly` and `yearly` if we take the example above).

## Bounties

We love to support community contributions to Open Collective in all kinds of ways, including translation! You can get paid for helping out. Please follow this process:

1. [Email us](mailto:support@opencollective.com) to let us know you're interested in working on translation for a bounty, and let us know which language.
2. Once we approve your request, translate the content on Crowdin as described above.
3. Email us again when you've reached 100%.
4. We will ask another speaker of your language to check your translation.
5. If it all looks good, submit an expense for up to $200 to the [Comms & Docs](https://opencollective.com/comms-docs) Collective (you can decide to claim the full amount, or less, depending on how much time you spent).
6. We will pay you!
