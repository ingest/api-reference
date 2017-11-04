# Retrieve Event Types

Returns a list of all possible events as shown in [Supported Events](supported.md).

**URL** : `/events/types`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : `read_events`

## Success Response

**Code** : `200 OK`

**Response example**

Returns the list of event types.

```json
{
  "events": [
    "users.delete",
    "videos.create",
    "videos.update",
    "videos.delete",
    "videos.thumbnails.create",
    "videos.thumbnails.delete",
    "inputs.create",
    "inputs.complete",
    "inputs.update",
    "inputs.delete",
    "inputs.cancelled",
    "jobs.create",
    "jobs.error",
    "jobs.complete",
    "networks.update",
    "networks.update_status",
    "networks.users.create",
    "networks.users.delete",
    "networks.keys.create",
    "networks.keys.update",
    "networks.keys.delete",
    "profiles.create",
    "profiles.update",
    "profiles.delete",
    "roles.create",
    "roles.update",
    "roles.delete"
  ]
}
```
