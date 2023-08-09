# rate limit

To ensure fair usage and maintain the stability of the Coodo.xyz API, rate limiting is enforced on incoming requests. This helps prevent abuse and ensures a smooth experience for all users. Please adhere to the following rate limits based on your usage:

1.  IP Rate Limit:

    Each IP address is subject to a rate limit of `500 requests per minute`.
2.  User Rate Limit:

    Each user account is allowed a maximum of `100 requests per minute`.

If you exceed this limit, you will receive a <mark style="color:orange;">`429 Too Many Requests`</mark> response. To continue using the API, wait until the rate limit window resets.

It's important to note that rate limits are in place to maintain the quality of service for all users. If you consistently encounter rate limit issues, consider optimizing your API usage, reducing the frequency of requests, or contacting us to discuss your specific needs.
