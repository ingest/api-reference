# Returns a Live Stream Status

Retrieves the status of a single live stream identified by the ID.

**URL** : `/live/<id>/status`

**URL Parameters** : Include the live stream `id` in the URL of the `GET` request.

**Method** : `GET`

**Auth required** : YES

**Permissions required** : `read_live`


## Success Response

**Code** : `200 OK`

**Response example**

Returns the live stream status.

```json
{
    "status": "RUNNING"
}
```
