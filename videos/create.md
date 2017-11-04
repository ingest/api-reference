# Create a Video

Creates a new video resource.

**URL** : `/videos`

**Method** : `POST`

**Auth required** : YES

**Permissions required** : `write_videos`

**Request Body**

Provide a valid video resource object to be created.

```json
{
	"title": "Tears of Steel",
	"description": "A live-action/CGI short film.",
	"tags": [
		"4k",
		"CGI",
		"live-action"
	]
}
```

## Success Response

Returns the newly created video object.

**Code** : `201 Created`

**Response example**

```json
{
    "id": "344d0cb5-0c39-416c-8f80-70f0200b5c8c",
    "url": "https://api.ingest.io/videos/344d0cb5-0c39-416c-8f80-70f0200b5c8c",
    "title": "Tears of Steel",
    "description": "A live-action/CGI short film.",
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
			"4k",
			"CGI",
			"live-action"
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
}
```
