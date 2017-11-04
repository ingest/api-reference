# Update Inputs

Perform an update to an existing input resource. This method accepts partial updates, which means you’re not required to include fields that haven’t been altered. It is recommended to include the minimal representation of changes to conserve bandwidth.

**URL** : `/encoding/inputs/<id>`

**URL Parameters** : Include the input `id` in the URL of the `PATCH` request.

**Method** : `PATCH`

**Auth required** : YES

**Permissions required** : `write_inputs`

**Request Body**

Provide the patched Video resource object in the body of your request.

```json
{
	"filename": "bbb.mp4"
}
```

## Success Response

**Code** : `200 OK`

**Response example**

Updating an input to have the new filename "bbb.mp4", the entire updated input record will be returned:

```json
{
    "id": "6fd0f383-3807-42a3-8114-833db9135cb3",
    "url":
        "https://api.ingest.io/encoding/inputs/6fd0f383-3807-42a3-8114-833db9135cb3",
    "filename": "bbb.mp4",
    "type": "video/mp4",
    "path": "westeros/6fd0f383-3807-42a3-8114-833db9135cb3/input.mp4",
    "size": 1233637,
    "images": [{
        "thumbnail_id": "5610ca53-5701-4b57-bb66-07fe7bb2db8a",
        "thumbnail_url": "2d0fb3db-86f6-42fb-ae75-04cca701dadd/poster.jpg",
        "thumbnail_type": "system"
    }],
    "created_at": "2016-03-07T11:23:01.858484-04:00",
    "updated_at": "2016-05-13T11:20:06.269491-03:00",
    "network_id": "ddbc5c9f-90c6-4fed-b533-91b02753e271",
    "metadata": {
      "format": {
        "size": "1233637",
        "tags": {
          "encoder": "Lavf56.40.101",
          "major_brand": "isom",
          "minor_version": "512",
          "compatible_brands": "isomiso2avc1mp41"
        },
        "bit_rate": "657895",
        "duration": "15.001000",
        "filename": "pathtofile.mp4",
        "nb_streams": 2,
        "start_time": "0.000000",
        "format_name": "mov,mp4,m4a,3gp,3g2,mj2",
        "nb_programs": 0,
        "probe_score": 100,
        "format_long_name": "QuickTime / MOV"
      },
      "streams": [{
        "...":"..."
      }]
    },
    "last_used":"2016-05-13T11:20:06.269491-03:00"
}
```