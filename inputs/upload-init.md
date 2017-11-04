# Initialize an Upload

Initializes the process of uploading an input file for usage with Ingest. This operation supports direct upload, done in a single operation, or multipart upload, separating the file in parts and uploading each individually. Amazon recommends using Multipart uploads if your object size is over 100MB. For more information about the different delivery method you can reference Amazon’s [documentation](http://docs.aws.amazon.com/AmazonS3/latest/dev/UploadingObjects.html).

**URL** : `/encoding/inputs/<id>/upload`

**URL Parameters** :
- Include the input `id` in the URL of the `POST` request.
- Use the `type` query parameter to specify which delivery method you will use.

**Delivery Methods** :

| Value      | Description                                                                                    |
| ---------- | ----------------------------------------------------------------------------------------------:|
| `amazonMP` | Utilize direct upload via the Amazon Multipart API. Ingest will sign each individual request.  |
| `amazon`   | Utilize a direct upload via POST, you’ll receive a policy to allow uploads for a short period. |

**Method** : `POST`

**Auth required** : YES

**Permissions required** : `write_inputs`

**Request Body**

For Multipart uploads, the Ingest API returns the recommended number of parts for the file based on the size value, as well as the size of each part in bytes. This is a recommendation, however there is a minimum size of 5MB per part. The one exception to this rule is the last part of the file being uploaded.

```json
{
    "type": "video/mp4",
    "size": 1233637
}
```

## Success Response

Returns an object describing the path for resource upload, as well as information required for the `/encoding/inputs/<id>/upload/sign endpoint`.

**Code** : `201 Created`

**Response example**

Singlepart Response object:

```json
{
    "key": "https://..."
}
```

Multipart Response object:

```json
{
    "key": "https://...",
    "uploadId": "cfb8ai1-73bc-49f5-bb30-ak1672e9abi8",
    "pieceCount": 6,
    "pieceSize": 333637
}
```

## Notes

* When submitting the ID of a non existing input, an HTTP status of `404` will be returned.
