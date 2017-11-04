# Retrieve Webhooks For a Single Event

**URL** : `/hooks/<event>`

**URL Parameters** : Include the event `name` in the URL of the `GET` request.

**Method** : `GET`

**Auth required** : YES

**Permissions required** : `read_hooks`

## Success Response

**Code** : `200 OK`

**Response example**

Returns a list of webhook subscriptions for the passed event name `jobs.create`

```json
[
  {
    "network_id": "fed6e925-dee4-41cc-be4a-479cabc149a5",
    "event_name": "jobs.create",
    "url": "http://webhookendpoint.com",
    "enabled": true,
    "secret": "c5809b07684a0f73"
  },
  {
    "network_id": "fed6e925-dee4-41cc-be4a-479cabc149a5",
    "event_name": "jobs.create",
    "url": "http://anotherwebhookendpoint.com",
    "enabled": false,
    "secret": "ec3320a695ee73e0"
  }
]
```
