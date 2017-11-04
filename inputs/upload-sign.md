# Retrieve Signature for Upload

Retrieves a signature for uploading an input to the Ingest service. This represents the second step of an input upload, you can reference the Initialize Upload session for more information about the process.

**URL** : `/encoding/inputs/<id>/upload/sign`

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

Single part uploads do not require any additional information to construct the signature, however for multipart uploads you must provide the partNumber and uploadId via the POST body.

```json
{
    "partNumber": 1,
    "uploadId": "cfb8ai1-73bc-49f5-bb30-ak1672e9abi8",
    "contentMd5": "" // optional. if passed, used to verify integrity of each file
}
```

## Success Response

Returns an object containing the details to construct the request to begin upload.

**Code** : `200 OK`

**Response example**

```json
{
    "authHeader": "...", // The value you should set for the Authorization header
    "dateHeader": "...", // The value you should set for the x-amz-date header
    "url": "...", // URL you should use for the PUT request to upload this part
    "securityToken": "...", // The value you should set for the x-amz-security-token header
}
```

## Notes

* When submitting the ID of a non existing input, an HTTP status of `404` will be returned.
