# Retrieve Videos

Retrieves a list of videos for the authorized network.

**URL** : `/videos`

**URL Parameters** :
  - Pass the `search` parameter to search videos via title.
  - Use `status` to limit the result set to match the status, see available values below.
  - Passing `private` limits the result set to videos that require playback tokens. The only acceptable value is `true`.

**Status Values** :

| Name         | Description                                                                                         |
| ------------ | ---------------------------------------------------------------------------------------------------:|
| `created`    | Limits the set of videos to only include ones created but have no media associated.                 |
| `published`  | Limits the set of videos to only include ones which do not have a variant associated.               |
| `draft`      | Limits the set of videos to those which have finished encoding, they’re playable but not published. |
| `processing` | Limits the set of videos to only videos currently processing a media encode.                        |
| `trashed`    | Limits the set of videos to soft deleted videos.                                                    |
| `error`      | Limits the set of videos to those which have associated media attached which failed to encode.      |

**Method** : `GET`

**Auth required** : YES

**Permissions required** : `read_videos`

## Success Response

**Code** : `200 OK`

**Response example**

For videos apart of the authorized network.

```json
[{
    "id": "344d0cb5-0c39-416c-8f80-70f0200b5c8c",
    "url": "https://api.ingest.io/videos/344d0cb5-0c39-416c-8f80-70f0200b5c8c",
    "title": "Video Title",
    "description": "Description of Video",
    "playback_urls": [],
    "type": "hls",
    "status": "CREATED",
    "schedule_start": null,
    "schedule_end": null,
    "private": false,
    "genre": "Action",
    "content_type": null,
    "release_date": null,
    "runtime": null,
    "crew": null,
    "country": "Canada",
    "language": "English",
    "tags": [
      "action"
    ],
    "poster": {
      "thumbnail_id": "647214a4-15c7-41f9-ad59-7fba339bf3cf",
      "thumbnail_url": "https://play.ingest.io/westeros/df24eaeb-17b5-49d1-84af-2ac58f99a0e6/poster.jpg",
      "thumbnail_type": "system"
    },
    "author": "2b2f918f-77f2-4ff1-bc5e-171296d9ed29",
    "updater": "4df9e8d3-f2e2-467d-ae99-1c19908f164a",
    "variants": null,
    "created_at": "2016-10-29T18:46:21.71506Z",
    "updated_at": "2016-11-06T15:28:15.786327Z",
    "deleted_at": null,
    "published_at": "2015-10-29T18:46:21.71506Z"
}]
```

## Notes

* Listing videos is a paginated operation and also currently supports title-based searching via the query parameter search. As well, this operation accepts a query parameter to filter records based on status. This parameter can be comma-separated for multiple status values. By default the returned records will be filtered by status of `draft, published`.
