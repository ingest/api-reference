# Jobs Objects

## Example Request Object

```json
{
    "inputs": [
        "340dd145-c06b-4d72-a8cc-0f6b270eb065"
    ],
    "profile": "2876db3d-ed16-4cf2-af82-98a383009e3c",
    "video": "62dcb602-e95b-483c-badf-9497914717a5"
}
```

Attribute | Type       | Description
--------- |:----------:| ---------------------------------------------:|
inputs    | *[string]* | String array of input UUIDs                   |
profile   | *string*   | A UUID that references the profile resource   |
video     | *string*   | A UUID that references the video resource     |

## Example Response Object

```json
{
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
```

This is the expected format for all responses returning a job object.

Attribute  | Type       | Description                                                           |
---------- |:----------:| ---------------------------------------------------------------------:|
id         | *string*   | UUID of the job                                                       |
url        | *string*   | Self-referencing URL for job                                          |
status     | *integer*  | Representation of the current [status](#jobs-status) of the job       |
progress   | *integer*  | Progress of the encoding job                                          |
video      | *string*   | UUID of the video resource the encoding job targets                   |
inputs     | *[string]* | String array of UUIDs for the input resources the encoding job uses   |
created_at | *string*   | Date and time of creation                                             |
updated_at | *string*   | Date and time of last update                                          |
deleted_at | *string*   | Date and time of deletion                                             |

## Jobs status

Status  | Description
------- | -----------
0       | Job in progress
1       | Job completed successfully
10      | Job failed