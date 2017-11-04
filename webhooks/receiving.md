# Receiving Webhooks

When subscribing a Webhook URL make sure the server is accessible from the internet. The payload sent through HTTP POST request will have the following structure:

| Attribute      | Type     | Description                                                        |
| -------------- |:--------:| ------------------------------------------------------------------:|
| `event`        | *string* | The name of the event                                              |
| `URL`          | *string* | The Ingest API URL to retrieve the resource affected by the event. |
| `event_object` | *object* | Event object.                                                      |


Ingest will make up to 3 attempts to send the HTTP POST request to your registered webhook URL. If you wish to prevent future attempts, simply include the header `X-Ingest-No-Retry` with the response.

## Headers

Below is a list of headers included in webhook POST requests.

| Name                       | Description                                                                                   |
| -------------------------- | ---------------------------------------------------------------------------------------------:|
| `X-Ingest-Signature`       | Hexadecimal encoding of the SHA1 HMAC of the request body, using the `secret` as the key.     |
| `X-Ingest-Request-Attempt` | Number of HTTP POST requests attempts.                                                        |
| `X-Ingest-Retry-Reason`    | If second or third attempt, the value for this header is the reason why previous call failed. |

## X-Ingest-Signature

To validate the identity of the request Sender, compare the hex encoding of the SHA1 HMAC encryption of the request body, using your webhook `secret` as key, with the value of this Header.
