# Delete a Live Stream

Deletes a live stream resource, invalidating the stream key associated with it. The key will no longer be accepted by the RTMP server and any live feed being sent through it will be denied.
Optionally, you can include a `permanent=1` query parameter to permanently delete the live stream resource.


**URL** : `/live/<id>`

**URL Parameters** : Include the network `id` in the URL of the `DELETE` request.

**Query Parameters** : When permanently deleting a live stream, include the param `permanent=1`

**Method** : `DELETE`

**Auth required** : YES

**Permissions required** : `write_live`


## Success Response

**Code** : `202 Accepted`
