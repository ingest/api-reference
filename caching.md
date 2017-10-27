# Caching

API responses include an `ETag` (Entity Tag) header. This header identifies the specific version of a returned resource. If the resource has not changed since your last request, a `304 Not Modified` status will be returned. If the resource has changed, the request will proceed normally.
