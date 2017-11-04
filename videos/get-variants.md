# Retrieve media variants.

Retrieve all media variant groups for a specified video resource.

**URL** : `/videos/:id/variants`

**URL Parameters** : Include the video `id` in the URL of the `GET` request.

**Method** : `GET`

**Auth required** : YES

**Permissions required** : `read_videos`

## Success Response

**Code** : `200 OK`

**Response example**

For a video with the passed `id` of `e1ceb092-949f-4bf5-9292-50d524dc87de`:

```json
[
  {
    "id": "e7e86d8e-a69f-4091-8274-5f4c84d70262",
    "name": "low",
    "duration": 15.914667,
    "type": "hls",
    "video_id": "e1ceb092-949f-4bf5-9292-50d524dc87de",
    "profile_id": "bff33171-5658-4b39-aaf2-f0db8ebb0f31"
  },
  {
    "id": "b738bc43-88cf-4057-8432-0d26cc1490d6",
    "name": "medium",
    "duration": 15.914667,
    "type": "hls",
    "video_id": "e1ceb092-949f-4bf5-9292-50d524dc87de",
    "profile_id": "bff33171-5658-4b39-aaf2-f0db8ebb0f31"
  },
  {
    "id": "d328e4c8-62b1-413f-93fc-702fb74aef05",
    "name": "high",
    "duration": 15.914667,
    "type": "hls",
    "video_id": "e1ceb092-949f-4bf5-9292-50d524dc87de",
    "profile_id": "bff33171-5658-4b39-aaf2-f0db8ebb0f31"
  }
]
```
