# Retrieve A Live Stream

Retrieves one single live stream and a list of its members.

**URL** : `/live/<id>`

**URL Parameters** : Include the live stream `id` in the URL of the `GET` request.

**Method** : `GET`

**Auth required** : YES

**Permissions required** : `read_live`

## Success Response

**Code** : `200 OK`

**Response example**

```json
{
    "id": "bb1c1bc2-7932-48be-937e-d7605d27f4e8",
    "url": "https://api.ingest.i0/live/bb1c1bc2-7932-48be-937e-d7605d27f4e8",
    "stream_key": "zHABj7dbla12345",
    "title": "Live stream title",
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

## Notes

* When requesting the ID of a non existing live stream, an HTTP status of `404` will be returned.
