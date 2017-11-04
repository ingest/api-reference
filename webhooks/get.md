# Retrieve Webhooks

Returns a list of every webhook subscription

**URL** : `/hooks`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : `read_hooks`

## Success Response

**Code** : `200 OK`

**Response example**

Returns a list of all webhook subscriptions for currently authorized network.

```json
[
  {
    "network_id": "fed6e925-dee4-41cc-be4a-479cabc149a5",
    "event_name": "jobs.create",
    "url": "http://webhookendpoint.com",
    "enabled": true,
    "secret": "9338345e4a76552a"
  },
  {
    "network_id": "fed6e925-dee4-41cc-be4a-479cabc149a5",
    "event_name": "videos.delete",
    "url": "http://webhookendpoint.com",
    "enabled": false,
    "secret": "9f208e140b59d068"
  }
]
```
