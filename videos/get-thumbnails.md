# Retrieve a Video’s thumbnails

Retrieve all thumbnails associated with a video resource.

**URL** : `/videos/<id>/thumbnails`

**URL Parameters** : Include the video `id` in the URL of the `GET` request.

**Method** : `GET`

**Auth required** : YES

**Permissions required** : `read_videos`

## Success Response

**Code** : `200 OK`

**Response example**

For a video with the passed `id` of `2d0fb3db-86f6-42fb-ae75-04cca701dadd`:

```json
[{
  "thumbnail_id": "5610ca53-5701-4b57-bb66-07fe7bb2db8a",
  "thumbnail_url": "https://play.ingest.io/2d0fb3db-86f6-42fb-ae75-04cca701dadd/poster.jpg",
  "thumbnail_type": "system"
}]
```
