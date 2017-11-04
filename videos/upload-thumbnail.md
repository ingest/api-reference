# Upload a thumbnail

Uploads a supported image file to our hosted service to be used as a thumbnail for your video resource. Users are limited to 5 thumbnails upload, with each limited to 5MB. If a limit is reached, either an HTTP status of `412` or `413` will be returned.

Alongside uploading thumbnails to Ingest, we also support external thumbnails through the `/videos/:id/thumbnails` endpoint. Ingest accepts a few types of thumbnails, the acceptable types are listed below. If an unsupported thumbnail is sent a HTTP status of `400` is returned.

**URL** : `/videos/<id>/thumbnail`

**URL Parameters** : Include the video `id` in the URL of the `POST` request.

**Supported Extensions** :

| Extension    | Mimetype        |
| ------------ | ---------------:|
| `.jpg`       | `image/jpeg`    |
| `.png`       | `image/png`     |
| `.gif`       | `image/gif`     |
| `.bmp`       | `image/bmp`     |
| `.webp`      | `image/webp`    |

**Method** : `POST`

**Auth required** : YES

**Permissions required** : `write_videos`

**Request Body**

The Content-Type must be `multipart/form-data` and the request body contains the file data on the `image` key.

## Success Response

**Code** : `201 OK`

**Response example**

```json
{
  "thumbnail_id": "5610ca53-5701-4b57-bb66-07fe7bb2db8a",
  "thumbnail_url": "https://play.ingest.io/2d0fb3db-86f6-42fb-ae75-04cca701dadd/poster.jpg",
  "thumbnail_type": "system"
}
```
