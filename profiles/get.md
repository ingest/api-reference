# Retrieve Profiles

Retrieves a list of profiles. This operation accepts query parameters to filter returned results.

**URL** : `/encoding/profiles`

**URL Parameters** :
  - Use the `filter` query parameter with a value of `trashed` to return deleted profiles.
  - Use the `search` query parameter to return a list of profiles which names match the search input.

**Method** : `GET`

**Auth required** : YES

**Permissions required** : `read_profiles`

## Success Response

**Code** : `200 OK`

**Response example**

Returns a list of [profile objects](object.md) for the authorized users network.

## Notes

* Listing inputs is a paginated operation.
* If no filter is specified all non-deleted inputs are returned.
