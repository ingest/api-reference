# Pagination

All resource requests returning a list of objects will return a `Content-Range` header identifying the range of values returned. Depending on the amount of items present in a list, additional requests may be required to retrieve the remaining items. In that case, an HTTP status of `206 Partial Content` along with the `Next-Range` header will be returned.

To retrieve the next range of items, simply repeat the request and set the `Range` header to the value of the previous request’s `Next-Range` header.
