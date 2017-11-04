# Update Profiles

Updates an existing profile resource. As a PUT method, the entire profile resource is required to be passed.

**URL** : `/encoding/profiles/<id>`

**URL Parameters** : Include the input `id` in the URL of the `PUT` request.

**Method** : `PUT`

**Auth required** : YES

**Permissions required** : `write_profiles`

**Request Body**

*Reference the [profile object](object.md) for details related to the expected format of a profile object.*

## Success Response

**Code** : `200 OK`

**Response example**

Returns an updated [profile object](object.md).

## Notes

* When submitting the ID of a non existing profile, an HTTP status of `404` will be returned.
