# Events Object

## Example Object

```json
{
  "event_id": "a130ab7ce-0ae6-4550-b973-678cfaad68b9",
  "network_id": "fed6e925-dee4-41cc-be4a-479cabc149a5",
  "event_name": "jobs.create",
  "data":{
    "id": "b9fe1066-6d78-42e6-a833-8b015c5029e3",
    "url": "https://api.ingest.io/encoding/jobs/b9fe1066-6d78-42e6-a833-8b015c5029e3",
    "status": 0,
    "progress": 0,
    "profile": "2876db3d-ed16-4cf2-af82-98a383009e3c",
    "video": "62dcb602-e95b-483c-badf-9497914717a5",
    "inputs": [
      "340dd145-c06b-4d72-a8cc-0f6b270eb065"
    ],
    "created_at": "2016-03-03T13:36:26.012751Z",
    "updated_at": "2016-03-03T13:36:26.023127Z",
    "deleted_at": null
  }
}
```

| Attribute    | Type     | Description                                                    |
| ------------ |:--------:| --------------------------------------------------------------:|
| `event_id`   | *string* | The event ID                                                   |
| `network_id` | *string* | The network ID                                                 |
| `name`       | *string* | The name of the event                                          |
| `created_at` | *string* | Datetime of event creation                                     |
| `data`       | *object* | The JSON representation of the resource affected by the event. |


#### Events.Data Structure

In most cases, the `data` field will be the entire resource object. However, some events might contain different data structures. Listed below are what you should expect whenever the full resource is not included.
