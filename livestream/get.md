# Retrieve Live Streams

Retrieves a list of live streams. By default this operation returns every live stream record for the network, however, it is also possible to filter the list by status. You can pass a comma-separated list of status when searching for multiple statuses.

**URL** : `/live`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : `read_live`

**Query Parameters** : Optionally, include a `status` param with a comma-separated list of status you'd like to filter the list. Ex.: `status=running,idle`

Existing statuses are:

| Status    | Description                                                |
| --------- | ----------------------------------------------------------:|
| idle      | Limits the set of live streams to only return idle streams.
| running   | Limits the set of live streams to only return currently running streams.
| deleted   | Limits the set of live streams to only return soft-deleted streams.
| error     | Limits the set of live streams to only return live streams that resulted in error when starting/stopping a stream.

## Success Response

**Code** : `200 OK`

**Response example**

```json
[{
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
}]
```
