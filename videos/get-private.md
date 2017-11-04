# Check if a video is playback protected.

Returns just the `private` boolean for a video record, can be used for checking if a playback token needs to be generated for a user before requesting playback.

**URL** : `/videos/<id>/private`

**URL Parameters** : Include the video `id` in the URL of the `GET` request.

**Method** : `GET`

**Auth required** : YES

**Permissions required** : `read_videos`

## Success Response

**Code** : `200 OK`

**Response example**

For a video with the passed `id` of `2d0fb3db-86f6-42fb-ae75-04cca701dadd`:

```json
{
  "private": true
}
```
