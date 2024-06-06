# Data Export

{% hint style="danger" %}
With the implementation of the new [Dashboard interface](https://docs.opencollective.com/help/product/understanding-your-dashboard), we are currently in the process of updating our documentation and some pages may be out of date. Thank you for your patience. Please [contact](https://opencollective.com/contact) our support team if you need any assistance.
{% endhint %}

There are multiple ways to export your collectives data. Download your contributor data, Transactions information and delve into your export settings.&#x20;

### Contributor Information

Navigate to your collective's Dashboard -> **Contributors**.&#x20;

<figure><img src="../../.gitbook/assets/Untitled design (10).png" alt=""><figcaption></figcaption></figure>

Click on the Export CSV button in top right hand corner. \


**The CSV export contains:**&#x20;

* Contributor Profile URL&#x20;
* Contributor Name&#x20;
* Contributor Type (Individual or Company)
* Total Amount Contributed
* Currency&#x20;
* Active Recurring Contribution&#x20;
* Recurring Contribution Tier
* Recurring Contribution Amount
* Recurring Contribution Frequency
* First Contribution Date
* Latest Contribution Date&#x20;
* Email&#x20;
* Website

## Exporting Transactions

Head to the budget section on your collective page. Click the Transactions tab

![](../../.gitbook/assets/collectives\_dataexport\_transactions\_2022-07-28.png.png)

&#x20;2\. Click View all Transactions&#x20;

![](../../.gitbook/assets/collectives\_dataexport\_viewtransactions\_2022-07-28.png)



3\. Apply any filters to the CSV export.&#x20;

_For example select expenses in the Kind type to export a CSV with your expense information._&#x20;

![](../../.gitbook/assets/collectives\_Expenses\_viewtransactions\_2022-07-28.png.png)

4\. Download CSV on the right

## Export Settings

Navigate to your collective's dashboard -> Settings -> **Export**.

<figure><img src="../../.gitbook/assets/Untitled design (9).png" alt=""><figcaption></figcaption></figure>

On this page, you can export your data into:

* Contributor data CSV Export&#x20;
* JSON Export
* Widgets
* Badges
* Contributors images

#### Export Contributors CSV

Download a file of all of your contributors, with these fields:

* Member ID
* Date Created
* User Type (User or Organisation)&#x20;
* Role (Admin, Host, Backer, Follower)&#x20;
* Tier
* Active Recurring Contribution&#x20;
* Total Amount Donated
* Currency
* Lastest Transaction Date
* Lastest Transaction Amount
* User Profile URL
* Name
* Company
* Description
* Image
* Email
* Newsletter Opt in
* Twitter
* Github
* Website

#### Export JSON

Export your data to integrate with other applications.

Options:

* All members (contributors of all types)
* Only users (individuals)
* Only organizations

Parameters:

* limit: number of members to return
* offset: number of members to skip (for paging)
* TierId: only return the members that belong to this TierId. You can find the TierId as part of the URL after selecting a tier on your collective pag

#### Widget

Export an HTML script to use on your website, showing your financial contributors.

![](<../../.gitbook/assets/Screen Shot 2019-05-31 at 11.59.36 AM.png>)

#### Export images

#### Badge

Create an SVG showing the number of financial contributors of your Collective. By updating the text in the URL, you can change the label and color.

Code:

`https://opencollective.com/collective/tiers/backers/badge.svg?label=Backers&color=brightgreen`

Result:

![](<../../.gitbook/assets/Screen Shot 2019-05-31 at 12.05.35 PM.png>)

#### Contributor image

Create an SVG showing the icons of your financial contributors.

There are a range of options:

| Parameter    | Description                                          | default     |
| ------------ | ---------------------------------------------------- | ----------- |
| width        | width of the image                                   |             |
| height       | height of the image                                  |             |
| limit        | max number of members to show                        | (unlimited) |
| avatarHeight | max height of each avatar / logo                     |             |
| button       | show "become a backer/sponsor" button                | true        |
| format       | format of the image (replace .svg with .png or .jpg) |             |

Code:

`<object type="image/svg+xml" data="https://opencollective.com/collective/tiers/backers.svg?avatarHeight=36&width=600"></object>`

Result:

![](<../../.gitbook/assets/Screen Shot 2019-05-31 at 12.09.13 PM.png>)

