# Count Inputs

Returns the number of inputs in the authorized network. This operation accepts a query parameter to filter results. The response is returned in the form of a `Resource-Count` header. If no filter is specified, all inputs associated with your network are returned.

**URL** : `/encoding/inputs`

**URL Parameters** :
  - Use `filter` to limit the result set to match the status, see available values below.

**Status Values** :

| Name         | Description                                                                     |
| ------------ | -------------------------------------------------------------------------------:|
| `video-only` | Will filter the count to inputs that must contain only video streams.           |
| `audio-only` | Will filter the count to inputs that must contain only audio streams.           |
| `has-video`  | Will filter the count to inputs that must contain at least one video stream.    |
| `has-audio`  | Will filter the count to inputs that must contain at least one audio stream.    |
| `trashed`    | Will filter the count to inputs that are marked for deletion.                   |
| `uploading`  | Will filter the count to inputs that are currently uploading.                   |
| `queued`     | Will filter the count to inputs that are currently queued.                      |
| `processing` | Will filter the count to inputs that are currently processing.                  |
| `error`      | Will filter the count to inputs that have encountered an error.                 |
| `ready`      | Will filter the count to inputs that have been processed.                       | 

**Method** : `HEAD`

**Auth required** : YES

**Permissions required** : `read_inputs`

## Success Response

**Code** : `204 OK`

**Response example**

For inputs counted in the authorized network. The following header is returned

```json
Resource-Count: 20
```
