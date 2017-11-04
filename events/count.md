# Count Events

Returns the number of events in the authorized network. This is returned in the form of a `Resource-Count `header.

**URL** : `/events`

**Method** : `HEAD`

**Auth required** : YES

**Permissions required** : `read_events`

## Success Response

**Code** : `204 OK`

**Response example**

For events counted in the authorized network. The following header is returned

```json
Resource-Count: 20
```
