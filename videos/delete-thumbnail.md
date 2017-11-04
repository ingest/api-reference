# Remove thumbnail from video

Removes a video thumbnail permanently. If the resource being deleted is the video’s current poster, an HTTP status of precondition failed: `412` will be returned.

**URL** : `/videos/<id>/thumbnail/<id>`

**URL Parameters** : Include the video `id` as the first ID param in URL of the `DELETE` request and the thumbnail ID in the second.

**Method** : `DELETE`

**Auth required** : YES

**Permissions required** : `write_videos`

## Success Response

**Code** : `202 Accepted`
