# Retrieve a Single Profile

Retrieve a single profile object.

**URL** : `/encoding/profiles/<id>`

**URL Parameters** : Include the profile `id` in the URL of the `GET` request.

**Method** : `GET`

**Auth required** : YES

**Permissions required** : `read_profiles`

## Success Response

**Code** : `200 OK`

**Response example**

Returns a matching [profile object](object.md).

## Notes

* When requesting the ID of a non existing profile, an HTTP status of `404` will be returned.
