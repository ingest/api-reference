# Retrieve all Events

Returns a list of all events that have been generated by the network.

**URL** : `/events`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : `read_events`

## Success Response

**Code** : `200 OK`

**Response example**

Returns the list of events for the authorized network.

```json
[
  {
    "event_id": "a130ab7ce-0ae6-4550-b973-678cfaad68b9",
    "network_id": "fed6e925-dee4-41cc-be4a-479cabc149a5",
    "event_name": "jobs.create",
    "created_at": "2017-03-10T16:04:10.331802-03:00",
    "data":{
      "id": "b9fe1066-6d78-42e6-a833-8b015c5029e3",
      "url": "https://api.ingest.io/encoding/jobs/b9fe1066-6d78-42e6-a833-8b015c5029e3",
      "status": 0,
      "progress": 0,
      "profile": "2876db3d-ed16-4cf2-af82-98a383009e3c",
      "video": "62dcb602-e95b-483c-badf-9497914717a5",
      "inputs": [
        "340dd145-c06b-4d72-a8cc-0f6b270eb065"
      ],
      "created_at": "2016-03-03T13:36:26.012751Z",
      "updated_at": "2016-03-03T13:36:26.023127Z",
      "deleted_at": null
      }
    },
  {
    "event_id": "a601895c-563b-45ea-8b0c-5d2a1ac5ec0f",
    "network_id": "fed6e925-dee4-41cc-be4a-479cabc149a5",
    "event_name": "videos.update",
    "created_at": "2017-04-18T10:40:49.175364-03:00",
    "data": {
      "id": "c01d322f-ee15-4df2-b182-963a9c6d5faf",
      "url": "https://api.ingest.io/videos/f01d322f-ee15-4df2-b182-963a9c6d5faf",
      "deleted_at": null,
      "title": "Test2",
      "description": "description",
      "variant_urls": [
        {
          "name": "high",
          "url": "https://play.ingest.info/videos/faa87672-76eb-453a-b0a6-1a55b1cb15ff/c01d322f-ee15-4df2-b182-963a9c6d5faf.mp4?name=high"
        },
        {
          "name": "medium",
          "url": "https://play.ingest.info/videos/faa87672-76eb-453a-b0a6-1a55b1cb15ff/c01d322f-ee15-4df2-b182-963a9c6d5faf.mp4?name=medium"
        },
        {
          "name": "low",
          "url": "https://play.ingest.info/videos/faa87672-76eb-453a-b0a6-1a55b1cb15ff/c01d322f-ee15-4df2-b182-963a9c6d5faf.mp4?name=low"
        }
      ],
      "type": "mp4",
      "status": "DRAFT",
      "schedule_start": "2017-02-01T11:04:05.000000-04:00",
      "schedule_end": "2017-03-01T11:04:05.000000-04:00",
      "private": true,
      "genre": "Comedy",
      "content_type": "Test, Movie",
      "release_date": "2017-04-17T21:00:00.000000-03:00",
      "runtime": "00:00:15.914667",
      "crew": "cast & crew",
      "country": "CA",
      "language": "English",
      "tags": [],
      "poster": {
        "thumbnail_id": "589c2701-906d-48cb-958d-f605d7866779",
        "thumbnail_url": "https://play.ingest.info/faa87672-76eb-453a-b0a6-1a55b1cb15ff/c01d322f-ee15-4df2-b182-963a9c6d5faf/poster1.png",
        "thumbnail_type": "system"
      },
      "author": "43e509f6-b4e9-4753-8bfa-6bfb39850e30",
      "updater": "43e509f6-b4e9-4753-8bfa-6bfb39850e30",
      "variants": [],
      "created_at": "2017-04-18T10:31:04.063095-03:00",
      "updated_at": "2017-04-18T10:40:48.928873-03:00"
    }
  },
]
```