# Time

The Ingest API always uses dates that conform to the [RFC3339](https://www.ietf.org/rfc/rfc3339.txt) standard. This is to ensure a clear representation of time.

Resources that are created in Ingest will always contain three timestamps, they represent when the resource was created, when was the last time the resource was updated, and when the record was disabled / soft-deleted.

```json
{
  "created_at": "2016-10-29T18:46:21.71506Z",
  "updated_at": "2016-11-06T15:28:15.786327Z",
  "deleted_at": null
}
```
