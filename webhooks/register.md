# Registering a Webhook endpoint

The webhook registration endpoint can subscribe one single URL to multiple events. If you’d like to subscribe multiple URLs to the same event, you can make sequential POST requests to this endpoint.

You have the option to include a security key to be used for identity verification when receiving webhooks, however if you don’t provide one Ingest will generate it automatically.

**URL** : `/hooks`

**Method** : `POST`

**Auth required** : YES

**Permissions required** : `write_hooks`

**Request Body**

```json
{
  "event_names": ["jobs.create", "jobs.error", "jobs.complete"],
  "url": "http://mywebhookendpoint.com",
  "enabled":true,
}
```

## Success Response

**Code** : `201 Created`
