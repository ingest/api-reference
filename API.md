# Ingest API Reference

The REST API empowers developers to access, extend, and combine Ingest with other services and media players. You can use the Ingest API to perform any task that our service can perform. The API is based on REST principles. We make use of built-in HTTP features such as HTTP authentication and HTTP status codes.

JSON is returned by all API responses, however this may be different where our SDKs convert responses to language-specific objects.

## API Location

`https://api.ingest.io`

## Features
* [Time](time.md)
* [Roles & Permissions](roles-and-permissions.md)
* [Request IDs](request-ids.md)
* [Pagination](pagination.md)
* [Versioning](versioning.md)
* [Caching](caching.md)
* [Rate Limiting](rate-limiting.md)

## Resources

### Live Stream

Ingest's live stream feature receives an RTMP stream as input and transcodes content to HLS format. Upon creation of a live stream resource, a stream key is generated, which will serve as your authentication point to our RTMP server. Any publishing from an invalid stream key will be disconnected.

You can check out our ["How To Go Live"](https://github.com/ingest/how-to-go-live) tutorial for more information on setting up your live stream with Ingest.

* [Get Live Streams](livestream/get.md) : `GET /live`
* [Get Live Stream](livestream/get-single.md) : `GET /live/<id>`
* [Get Live Stream Status](livestream/get-status.md) : `GET /live/<id>/status`
* [Create Live Stream](livestream/create.md) : `POST /live`
* [Update Live Stream](livestream/update.md) : `PATCH /live/<id>`
* [Delete Live Stream](livestream/delete.md) : `DELETE /live/<id>`

### Networks

Every user of the Ingest service belongs to one or more network. Every operation is restricted to the networks affiliated to the requesting user and the currently authenticated network. Through the API you are able to create, update and list networks, as well as manage their members.

* [Get Networks](networks/get.md) : `GET /networks`
* [Get Network](networks/get-single.md) : `GET /networks/<id>`
* [Update Network](networks/update.md) : `PATCH /networks/<id>`
* [Invite new user to Network](networks/user-invite.md) : `POST /networks/<id>/invite`
* [Add existing user to Network](networks/user-add.md) : `LINK /networks/<id>`
* [Remove user from Network](networks/user-remove.md) : `UNLINK /networks/<id>`

### Videos
