# Count Videos

Returns the number of videos belonging to the authorized network. This operation accepts a query parameter to filter records based on status. This parameter can be comma-separated for multiple status values. By default the returned records will be filtered by status of `draft, published`.

**URL** : `/videos`

**URL Parameters** :
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

**Method** : `HEAD`

**Auth required** : YES

**Permissions required** : `read_videos`

## Success Response

**Code** : `204 OK`

**Response example**

For videos counted in the authorized network. The following header is returned

```json
Resource-Count: 20
```
