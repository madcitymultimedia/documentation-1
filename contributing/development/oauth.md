---
description: >-
  OAuth lets you create applications that can access Open Collective's API to
  read information and trigger changes on the platform.
---

# OAuth

## Creating an OAuth app

1. Go to `https://opencollective.com/{account}/admin/for-developers` (replace `{account}` by the slug of the account you want to use as the owner of the app)
2. Click on `+ Create OAuth app` and fill in the required information\
   <img src="../../.gitbook/assets/image (53).png" alt="" data-size="original">
3. On the success page, copy the client ID and secret for later use

![](<../../.gitbook/assets/image (47).png>)

## Authorizing OAuth apps

Open Collective's OAuth implementation supports the standard [authorization code grant type](https://tools.ietf.org/html/rfc6749#section-4.1).

The web application flow to authorize users for your app is:

1. Users are redirected to request their Open Collective identity
2. Users are redirected back to your site by Open Collective with special code shared in the URL
3. You exchange the received code for an OAuth token

### 1. Request a user's Open Collective identity

> GET [https://opencollective.com/oauth/authorize](https://opencollective.com/oauth/authorize)

#### **Parameters**

| Name            | Type   | Description                                                                                                                                                                                                                                                                     |
| --------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `client_id`     | string | **Required.** The client ID you copied after [creating your app](oauth.md#creating-an-oauth-app).                                                                                                                                                                               |
| `response_type` | string | **Required.** Only supported value for now is `code`                                                                                                                                                                                                                            |
| `redirect_uri`  | string | The URL in your application where users will be sent after authorization. If left out, Open Collective will redirect users to the callback URL configured in the OAuth Application settings. If provided, the redirect URL's host and port must exactly match the callback URL. |
| `scope`         | string | A comma-separated list of scopes. If not provided, `scope` defaults to an empty list.                                                                                                                                                                                           |
| `state`         | string | Use it to pass some state back to your application after redirecting and to protect against cross-site request forgery attacks (CSRF) by including an unguessable random string.                                                                                                |

### Users are redirected back to your site

After users accept your request, they're redirected back to your site with a temporary `code` passed as an URL query parameter as well as the `state` you provided in the previous step. The temporary code will expire after 5 minutes. If the states don't match, then a third party created the request, and you should abort the process.
