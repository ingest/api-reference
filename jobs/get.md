# Retrieve Jobs

Retrieves a list of jobs for the network of the authenticated user.

**URL** : `/encoding/jobs`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : `read_jobs`

## Success Response

**Code** : `200 OK`

**Response example**

Returns a list of jobs for the authorized network.

```json
[
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
]