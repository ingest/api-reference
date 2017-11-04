# Deleting Webhooks

Deletes a single webhook subscription.

**URL** : `/hooks`

**Method** : `DELETE`

**Auth required** : YES

**Permissions required** : `write_hooks`

**Request Body**

You must pass both the `event_name` and `url` properties for the webhook subscription.

```json
{
  "event_name": "jobs.create",
  "url": "http://mywebhookendpoint.com"
}
```

## Success Response

**Code** : `200 OK`
