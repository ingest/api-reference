# Rate Limiting

All endpoints in Ingest are controlled by rate-limiting. This is implemented in order to prevent clients from overloading server resources by requesting more API calls than allowed during a time interval.

If a client goes over the interval rate limit, an HTTP status code of `429 Too Many Requests` is returned to the client with an empty content body.

The interval rate limit is set by Ingest and cannot be altered by the client.

### HTTP Headers

Several HTTP Headers are returned to the client with each API response which describes the current rate limiting status:

| Parameter              | Description                                                                     |
| ---------------------- | -------------------------------------------------------------------------------:|
| X-RateLimit-Limit      | The maximum number of requests that the client can make during a time interval. |
| X-RateLimit-Remaining  | The number of requests left during the current time interval.                   |
| X-RateLimit-Reset      | The number of seconds before the current time interval resets.                  |
| Retry-After            | The number of seconds that the client must wait before retrying a request.      |

Note that the `Retry-After` header value is only set in the response when the rate limit has been reached and an HTTP status of `429 Too Many Requests` is being returned. This could be used by a client to determine how long to back off before retrying the original request again. The `Ratelimit-Remaining` value will be zero in this case as well.
