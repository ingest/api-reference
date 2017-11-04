# Count Profiles

Returns the number of profiles in the authorized network. This operation accepts a query parameter to filter results. The response is returned in the form of a `Resource-Count` header

**URL** : `/encoding/inputs`

**URL Parameters** :
  - Use the `filter` query parameter with a value of `trashed` to return deleted profiles.

**Method** : `HEAD`

**Auth required** : YES

**Permissions required** : `read_profiles`

## Success Response

**Code** : `204 OK`

**Response example**

For profiles counted in the authorized network. The following header is returned

```json
Resource-Count: 20
```
