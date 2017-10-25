# Invite a User to a Network

Invites a registered or new user to a specific network. The invited user gets notified by email that an invitation for joining a network is awaiting.

**URL** : `/networks/<id>/invite`

**URL Parameters** : Include the network `id` in the URL of the `POST` request.

**Method** : `POST`

**Auth required** : YES

**Permissions required** : `write_networks`

**Request Body**

Provide the name of the user to be invited and their email. All fields are required.

```json
{
	"name": "Samwell Tarly",
	"email": "sam.tarly@email.com"
}
```

## Success Response

**Code** : `204 No Content`
