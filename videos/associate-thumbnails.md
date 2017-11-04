# Associate external thumbnails

Adds an external image as a thumbnail. This operation does not store the image on our servers. You can add as many thumbnails as you want through this endpoint.

**URL** : `/videos/<id>/thumbnails`

**URL Parameters** : Include the video `id` in the URL of the `POST` request.

**Method** : `POST`

**Auth required** : YES

**Permissions required** : `write_videos`

**Request Body**

The request body should include a JSON array of URLs to associate with the video.

```json
[
  "https://mango.blender.org/wp-content/gallery/4k-renders/01_thom_celia_bridge.jpg?5421dd",
  "https://mango.blender.org/wp-content/gallery/4k-renders/02_dome.jpg?5421dd",
  "https://mango.blender.org/wp-content/gallery/4k-renders/15_scientists.jpg?5421dd"
]
```

## Success Response

**Code** : `201 OK`

**Response example**

```json
[
  "https://mango.blender.org/wp-content/gallery/4k-renders/01_thom_celia_bridge.jpg?5421dd",
  "https://mango.blender.org/wp-content/gallery/4k-renders/02_dome.jpg?5421dd",
  "https://mango.blender.org/wp-content/gallery/4k-renders/15_scientists.jpg?5421dd"
]
```
