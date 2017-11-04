# Complete an Upload

This operation is useful for upload methods where the system is unable to tell when the upload is complete, due to it being in multiple parts, or allowing pauses or resumes. In other words, the closing of the upload connection doesn’t necessarily mean the upload is complete. For these cases, when an input upload is complete, you call the complete action to signal that the upload is finalized, and the resulting file should be created.

**URL** : `/encoding/inputs/<id>/upload/complete`

**URL Parameters** : Include the input `id` in the URL of the `POST` request.

**Method** : `POST`

**Auth required** : YES

**Permissions required** : `write_inputs`

**Request Body**

Profile the `UUID` of the resource being uploaded in the body of the request on the `uploadId` key.

```json
{
    "uploadId": "cfb8ai1-73bc-49f5-bb30-ak1672e9abi8"
}
```

## Success Response

**Code** : `200 OK`

## Notes

* When submitting the ID of a non existing input, an HTTP status of `404` will be returned.
* If the upload isn’t properly canceled by the system, an HTTP status of `409` will be returned.
