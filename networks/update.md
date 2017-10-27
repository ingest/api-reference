# Update a Network

Updates a network.

**URL** : `/networks/<id>`

**URL Parameters** : Include the network `id` in the URL of the `PATCH` request.

**Method** : `PATCH`

**Auth required** : YES

**Permissions required** : `write_networks`

**Request Body**

Provide the new name of the Network being updated.

```json
{
	"name": "Kings Landing"
}
```

## Success Response

**Code** : `200 OK`

**Response example**

For a user associated with a network name `Westeros` updating to `Winterfell`, their update network and associated members will be returned:

```json
{
  "network_id": "01234567-89ab-cdef-0123-456789abcabc",
  "name": "Winterfell",
  "customer_id": "yourstripe_id",
  "members": [
    {
      "id": "7e6a84ab-7f9e-470e-82e7-456789abcdef",
      "url": "https://dashboard.ingest.io/users/7e6a84ab-7f9e-470e-82e7-456789abcdef",
      "email": "jon.snow@email.com",
      "name": "Jon Snow",
      "profile": {
        "display_name": "Jon Snow",
        "title": "Brother of the Night’s Watch",
        "phone_number": "902 222-5555"
      },
      "timezone": "America/Halifax",
      "deleted_at": null
    },
    {
      "id": "4df9e8d3-f2e2-467d-ae99-456789abc123",
      "url": "https://dashboard.ingest.io/users/4df9e8d3-f2e2-467d-ae99-456789abc123",
      "email": "arya.stark@email.com",
      "name": "Arya Stark",
      "profile": {
        "display_name": "Arya Stark",
        "title": "No one"
      },
      "timezone": "America/Halifax",
      "deleted_at": null
    }
	]
}
```

## Notes

* When requesting the ID of a non existing network, an HTTP status of `404` will be returned.
