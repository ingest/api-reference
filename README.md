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

### Events

If your account is subscribed to webhooks, Ingest will create events according to changes happening to your network and notify you through HTTP POST requests.

[*Event Object*](events/object.md)

* [Supported Events](events/supported.md)
* [Count Events](events/count.md) : `HEAD /events`
* [Get Events](events/get.md) : `GET /events`
* [Get Event](events/get-single.md) : `GET /events/<id>`
* [Retrieve Event Types](events/get-types.md) : `GET /events/types`

### Inputs

Inputs are used in conjunction with Profiles and Jobs as part of Ingest’s Encoder. You can upload video, audio and subtitle tracks to use as inputs by the API. Supported operations include creating, reading, updating, and deleting inputs.

* [Count Inputs](inputs/count.md) : `HEAD /inputs`
* [Get Inputs](inputs/get.md) : `GET /inputs`
* [Get Input](inputs/get-single.md) : `GET /inputs/<id>`
* [Create Input](inputs/create.md) : `POST /encoding/inputs`
* [Update Input](inputs/update.md) : `PATCH /encoding/inputs/<id>`
* [Delete Input](inputs/delete.md) : `DELETE /encoding/inputs/<id>`
* [Initialize Upload](inputs/upload-init.md) : `POST /encoding/inputs/<id>/upload`
* [Sign Upload](inputs/upload-sign.md) : `POST /encoding/inputs/<id>/upload/sign`
* [Complete Upload](inputs/upload-complete.md) : `POST /encoding/inputs/<id>/upload/complete`
* [Abort Upload](inputs/upload-abort.md) : `POST /encoding/inputs/<id>/upload/abort`

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

### Profiles

Profiles are viewed by Ingest as the settings which configure the Encoding process. Use of the `/encoding/profiles` resource allows a user to describe exactly what settings should be used when producing the final renditions that will be streamed to the end user.

Also introduced in profiles is the concept of variant playlists. In the adaptive bitrate streaming technologies supported by Ingest, you need master playlists to run a smooth streaming process. Ingest takes this concept one step further, allowing a user to create multiple versions of these playlists, which we call variants.

The example profile creates two HLS master playlists. One called `low` and the other `medium`, each representing varying qualities and supporting different renditions. Another potential use-case for this is to target specific user-agents that may have limitations. A notable example of this would be the Roku 3, which is unable to play audio that has more than two channels.

If this was a target for your streaming needs, it would be simple to configure a variant playlist to serve specifically Roku users of your application.

[*Profiles Object*](profiles/object.md)

* [Count Profiles](profiles/count.md) : `HEAD /encoding/profiles`
* [Get Profiles](profiles/get.md) : `GET /encoding/profiles`
* [Get Profile](profiles/get-single.md) : `GET /encoding/profiles/<id>`
* [Create Profile](profiles/create.md) : `POST /encoding/profiles`
* [Update Profile](profiles/update.md) : `PUT /encoding/profiles/<id>`
* [Delete Profile](profiles/delete.md) : `DELETE /encoding/profiles/<id>`

### Videos

The video resource for the Ingest service is a core component of our offering. It allows a user of Ingest to store metadata related to their video content in a single source for easy presentation to their end-users.

Our encoder uses the Video resource as the output location for the final media entity you use for playback. You can find more information about the encoding process on the Inputs, Profiles, and Jobs sections of the documentation.

* [Count Videos](videos/count.md) : `HEAD /videos`
* [Get Videos](videos/get.md) : `GET /videos`
* [Get Video](videos/get-single.md) : `GET /videos/<id>`
* [Create Video](videos/create.md) : `POST /videos`
* [Update Video](videos/update.md) : `PATCH /videos/<id>`
* [Delete Video](videos/delete.md) : `DELETE /videos/<id>`
* [Get Thumbnails](videos/get-thumbnails.md) : `GET /videos/<id>/thumbnails`
* [Upload Thumbnail](videos/upload-thumbnail.md) : `POST /videos/<id>/thumbnail`
* [Associate Thumbnails](videos/associate-thumbnails.md) : `POST /videos/<id>/thumbnails`
* [Delete Thumbnail](videos/delete-thumbnail.md) : `DELETE /videos/<id>/thumbnail/<id>`
* [Get Private State](videos/get-private.md) : `GET /videos/<id>/private`
* [Get Variants](videos/get-variants.md) : `GET /videos/<id>/variants`

### Webhooks

The Webhooks API can be used to be notified about any event that may happen to your network.
Simply subscribe to one or more events by registering your webhook endpoint, and we will send an HTTP POST request to the specified URL containing the appropriate payload.

#### Security

As a way to validate the identity of the request, Ingest will include a Header X-Ingest-Signature containing a hex encoded HMAC of the request body. The SHA1 HMAC encryption is done using a secret key, generated during the webhook subscription.

If you don’t provide one during the registration process we will generate it automatically and return it with the response body.

* [Register A Webhook](webhooks/register.md) : `POST /hooks`
* [Get Webhooks](webhooks/get.md) : `GET /hooks`
* [Get Webhook](webhooks/get-single.md) : `GET /hooks/<event>`
* [Update A Webhook](webhooks/update.md) : `PATCH /hooks`
* [Remove a Webhook](webhooks/remove.md) : `DELETE /hooks`
* [Receiving a Webhook](webhooks/receiving.md)
