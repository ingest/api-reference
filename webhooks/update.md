# Updating Webhooks

Updates a webhook subscription.

**URL** : `/hooks`

**Method** : `PATCH`

**Auth required** : YES

**Permissions required** : `write_hooks`

**Request Body**

Because we allow multiple subscriptions per event, you must include both the event_name and url of the hook being updated.

```json
{
  "event_name": "jobs.create",
  "url": "http://mywebhookendpoint.com",
  "enabled":false,
}
```

## Success Response

**Code** : `200 OK`
