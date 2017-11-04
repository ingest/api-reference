# Delete a Video

Removes a video resource from Ingest. This operation initially “trashes” the video resource, making it unavailable for regular calls in the API, and schedules it for permanent removal in two weeks. If you wish to immediately remove a video and its associated media resources from Ingest, you can indicate this with a query parameter on this call.

**URL** : `/videos/<id>`

**URL Parameters** : Include the video `id` in the URL of the `DELETE` request.

**Query Parameters** : When permanently deleting a video, include the parameter `permanent=1`

**Method** : `DELETE`

**Auth required** : YES

**Permissions required** : `write_videos`

## Success Response

**Code** : `202 Accepted`
