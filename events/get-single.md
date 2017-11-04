# Retrieve a Single Event

Ingest webhooks system will send an HTTP POST request with the event payload to your registered URL. Although you should be able to retrieve any information about the event directly from the payload, it’s also possible to retrieve an event information through this endpoint.

**URL** : `/events/<id>`

**URL Parameters** : Include the event `id` in the URL of the `GET` request.

**Method** : `GET`

**Auth required** : YES

**Permissions required** : `read_events`

## Success Response

**Code** : `200 OK`

**Response example**

Returns a matching [event object](object.md).

## Notes

* When requesting the ID of a non existing event, an HTTP status of `404` will be returned.
