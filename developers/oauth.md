---
description: >-
  OAuth lets you create applications that can access Open Collective's API to
  read information and trigger changes on the platform.
---

# OAuth

## Creating an OAuth app

1. Go to `https://opencollective.com/{account}/admin/for-developers` (replace `{account}` by the slug of the account you want to use as the owner of the app)
2. Click on `+ Create OAuth app` and fill in the required information\
   <img src="../.gitbook/assets/image (53).png" alt="" data-size="original">
3. On the success page, copy the client ID and secret for later use

![](<../.gitbook/assets/image (47).png>)

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

### 2. Users are redirected back to your site

After users accept your request, they're redirected back to your site with a temporary `code` passed as an URL query parameter as well as the `state` you provided in the previous step. The temporary code will expire after 5 minutes. If the states don't match, then a third party created the request, and you should abort the process.

Otherwise, you can exchange the `code` you received as a parameter for an access token:

> POST [https://opencollective.com/oauth/token](https://opencollective.com/oauth/token)

#### Parameters

| Parameter       | Type   | Description                                                                                                                              |
| --------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| `grant_type`    | string | **Required.** The only supported value for now is `authorization_code`                                                                   |
| `client_id`     | string | **Required.** The client ID of your OAuth application (from [Creating an OAuth App](oauth.md#creating-an-oauth-app))                     |
| `client_secret` | string | **Required.** The client secret of you OAuth application (from [Creating an OAuth App](oauth.md#creating-an-oauth-app))                  |
| `code`          | string | **Required.** The code you received as a response to [Step 1](oauth.md#1.-request-a-users-open-collective-identity), after the redirect) |
| `redirect_uri`  | string | The URL in your application where users are sent after authorization.                                                                    |

#### Response

If the request succeeds, you'll receive an HTTP 200 response code with a JSON payload like:

```json
{
  "access_token": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```

This `access_token` is a [JWT token](https://fr.wikipedia.org/wiki/JSON\_Web\_Token) that you can decode to retrieve an object like this:

```json
{
  "access_token": "test_oauth__af45baf7e0dc98d362c373800e34e7e18d8b38dc18f6e4dbb304",
  "iat": 1640995200,
  "exp": 1648771200,
  "sub": "1"
}
```

The `access_token` contained in this JWT is the one that you want to use to access the API.

### 3. Use the access token to access the API

The access token allows you to make requests to the API on a behalf of a user on our public GraphQL API.

```
Authorization: Bearer {ACCESS_TOKEN}
GET https://api.github.com/user
```

For example, in curl you can set the Authorization header like this:

```shell
curl 'https://opencollective.com/api/graphql/v2' \
  -H 'authorization: Bearer {ACCESS_TOKEN}' \
  -H 'content-type: application/json' \
  -d '{"query": "{ me { id name email } }"}'
```
