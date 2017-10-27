# Retrieve Networks

Retrieves every network associated to the user making the request.

**URL** : `/networks`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : `read_networks`

## Success Response

**Code** : `200 OK`

**Response example**

For a user associated with a network name `Westeros`.

```json
[{
	"network_id": "01234567-89ab-cdef-0123-456789abcabc",
	"name": "Westeros",
	"customer_id": "yourstripe_id"
}]
```
