# authorization

The Coodo.xyz API uses Bearer token authentication to ensure secure access to its resources. To use the API, you'll need to include an access token with each request.

Access tokens are issued to users when they log in to the Coodo.xyz website. The token can be included in the `Authorization` header of your API requests, like this:

```
Authorization: Bearer <access_token>
```

Replace with the token provided to you by Coodo.xyz.

If you make a request without a valid access token or with an expired access token, you'll receive a <mark style="color:orange;">`401 Unauthorized`</mark> response. In that case, you'll need to obtain a new access token by logging in again.

Note that access tokens are valid for a limited time and will expire after a certain period of inactivity. Be sure to check the expiration time of your token and refresh it as needed.

We take security very seriously at Coodo.xyz, and we encourage you to follow best practices when using our API. Keep your access token secure and do not share it with anyone else. If you suspect that your access token has been compromised, please contact our support team immediately.
