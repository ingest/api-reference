# Abort an Upload

Aborts an input multipart upload.

**URL** : `/encoding/inputs/<id>/upload/abort`

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

**Code** : `201 Created`

## Notes

* When submitting the ID of a non existing input, an HTTP status of `404` will be returned.
* If the upload isn’t properly canceled by the system, an HTTP status of `409` will be returned.
