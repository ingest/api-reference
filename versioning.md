# Versioning

Ingest is a versioned API. To access the different versions of the API, you pass a different `Accept` header in the form `application/vnd.ingest.v[0-9+]+json`. As we make backwards-incompatible changes to our API, we will release a new version by incrementing the above.

The current version is `application/vnd.ingest.v1+json`. As new versions are released, it is possible that old API’s will become deprecated. We will provide notice of at least 60 days via a HTTP header `Ingest-Deprecate`, and a public announcement that will be sent to your network administrators.

It is a requirement for all requests to specify the version of the API they would like to access, if a request does not include a valid `Accept` header an HTTP status code of `406` will be returned.
