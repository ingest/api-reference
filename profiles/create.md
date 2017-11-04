# Create a Profile

Creates a new encoding profile.

**URL** : `/encoding/profile`

**Method** : `POST`

**Auth required** : YES

**Permissions required** : `write_profiles`

**Request Body**

Provide a valid [profile object](object.md) to be created.

```json
{
  "text_tracks": [
    "webvtt",
    "dfxp",
    "cea-708",
    "cea-608"
  ],
  "data": {
    "playlists": [{
      "name": "low",
      "version": 3,
      "byte_range": true,
      "renditions": [
        1,
        2,
        3,
        9
      ],
      "iframe_playlist": true
    }]
  }
}
```

## Success Response

Returns the newly created [profile object](object.md).

**Code** : `201 Created`
