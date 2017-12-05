## Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: Token token=api_token_here"
```

```javascript

```

> Make sure to replace `api_token_here` with the user's API key.

WaniKani API uses API tokens to allow access to the API. Information returned by the API is scoped to the owner of the API token, the User, passed in the authorization.

The User can obtain their API token in [Settings / Account](https://www.wanikani.com/settings/account#public-api-key).

WaniKani API expects for the API token to be included in all API requests to the server in a header that looks like the following:

`Authorization: Token token=api_token_here`

<aside class="warning">
You must replace <code>api_token_here</code> with the User's API key.
</aside>