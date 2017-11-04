# Create a Live Stream

Creates a new live stream resource.

**URL** : `/live`

**Method** : `POST`

**Auth required** : YES

**Permissions required** : `write_live`

**Request Body**

Provide the title of the live stream to be created. Title field is required.

```json
{
	"title": "Live Stream Title Here"
}
```

## Success Response

Returns the newly created live stream object.

**Code** : `201 Created`

**Response example**

```json
{
    "id": "bb1c1bc2-7932-48be-937e-d7605d27f4e8",
    "url": "https://api.ingest.i0/live/bb1c1bc2-7932-48be-937e-d7605d27f4e8",
    "stream_key": "zHABj7dbla12345",
    "title": "Live Stream Title Here",
    "network_id": "0bfac7d5-d78b-43e6-98d0-3cce91912345",
    "rtmp_url": "rtmp://live.ingest.io/origin/zHABj7dbla12345",
    "play_url": "https://stream.ingest.info/bb1c1bc2-7932-48be-937e-d7605d27f4e8/master.m3u8",
    "status": "IDLE",
    "created_at": "2017-09-11T12:11:04.975232Z",
    "finished_at": null,
    "deleted_at": null,
    "modified_at": null
}
```
