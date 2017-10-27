# Remove a User from a Network

Removes an existing user from a network. This operation invalidates any active authentication token the user may have for the network.

**URL** : `/networks/<id>`

**URL Parameters** : Include the network `id` in the URL of the `UNLINK` request.

**Method** : `UNLINK`

**Auth required** : YES

**Permissions required** : `write_networks`

**Request Body**

Provide the id of the user to be removed from the network. This is required.

```json
{
  "id": "7e6a84ab-7f9e-470e-82e7-456789abcdef"
}
```

## Success Response

**Code** : `200 OK`

**Response example**

For a user associated with the network `Westeros` who just removed "Jon Snow", their network with updated member list will be returned:

```json
{
  "network_id": "01234567-89ab-cdef-0123-456789abcabc",
  "name": "Westeros",
  "customer_id": "yourstripe_id",
  "members": [
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

* If the user isn’t currently a member of the network, an HTTP status of `404` will be returned.
