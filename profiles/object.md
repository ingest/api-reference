# Profiles Object

## Example Object

```json
{
	"id": "0519d89d-ac2e-4cd7-938a-89c32e764c8a",
	"url": "https://api.ingest.io/encoding/profiles/0519d89d-ac2e-4cd7-938a-89c32e764c8a",
	"name": "Default Profile",
	"text_tracks": [
		"webvtt",
		"dfxp",
		"cea-708",
		"cea-608"
	],
	"data": {
		"playlists": [{
			"name": "low",
			"version": 3,
			"byte_range": true,
			"renditions": [
				1,
				2,
				3,
				9
			],
			"iframe_playlist": true
		}, {
			"name": "medium",
			"version": 3,
			"byte_range": true,
			"renditions": [
				1,
				2,
				3,
				4,
				5,
				6,
				9
			],
			"iframe_playlist": true
		}],
		"renditions": [{
			"id": 1,
			"audio": {
				"codec": "libfdk_aac",
				"bitrate": "64k",
				"channels": 2,
				"sample_rate": "48k"
			},
			"video": {
				"codec": "libx264",
				"width": 416,
				"height": 234,
				"bitrate": "200k",
				"profile": "baseline",
				"keyframe": 36,
				"framerate": 12,
				"codec_options": {},
				"keep_aspect_ratio": true
			},
			"streams": [
				"audio",
				"video",
				"captions"
			]
		}, {
			"id": 2,
			"audio": {
				"codec": "libfdk_aac",
				"bitrate": "64k",
				"channels": 2,
				"sample_rate": "48k"
			},
			"video": {
				"codec": "libx264",
				"width": 480,
				"height": 270,
				"bitrate": "400k",
				"profile": "baseline",
				"keyframe": 45,
				"framerate": 15,
				"codec_options": {},
				"keep_aspect_ratio": true
			},
			"streams": [
				"audio",
				"video",
				"captions"
			]
		}, {
			"id": 3,
			"audio": {
				"codec": "libfdk_aac",
				"bitrate": "64k",
				"channels": 2,
				"sample_rate": "48k"
			},
			"video": {
				"codec": "libx264",
				"width": 640,
				"height": 360,
				"bitrate": "600k",
				"profile": "baseline",
				"keyframe": 90,
				"framerate": 29.97,
				"codec_options": {},
				"keep_aspect_ratio": true
			},
			"streams": [
				"audio",
				"video",
				"captions"
			]
		}, {
			"id": 4,
			"audio": {
				"codec": "libfdk_aac",
				"bitrate": "96k",
				"channels": 2,
				"sample_rate": "48k"
			},
			"video": {
				"codec": "libx264",
				"width": 640,
				"height": 360,
				"bitrate": "1200k",
				"profile": "baseline",
				"keyframe": 90,
				"framerate": 29.97,
				"codec_options": {},
				"keep_aspect_ratio": true
			},
			"streams": [
				"audio",
				"video",
				"captions"
			]
		}, {
			"id": 5,
			"audio": {
				"codec": "libfdk_aac",
				"bitrate": "64k"
			},
			"streams": [
				"audio"
			],
			"byte_range": true
		}]
	},
	"digital_rights": {
		"type": "mpeg_cenc",
		"data": {
			"license_server_url": "valid url"
		}
	},
	"type": "hls",
	"created_at": "2016-02-25T19:44:28.53063Z",
	"updated_at": "2016-02-25T19:44:28.536324Z",
	"deleted_at": null
}
```

## HLS Profile

This is the expected format for responses returning a profile object:

| Attribute       | Type       | Description                                                             |
| --------------- |:----------:| -----------------------------------------------------------------------:|
| id              | *string*   | Profile UUID                                                            |
| url             | *string*   | Self-referencing URL for profile resource                               |
| name            | *string*   | Name to identify the profile                                            |
| text_tracks     | *[string]* | String array of subtitle formats to use for this profile                |
| digital_rights  | *object*   | DRM settings for this profile                                           |
| type            | *string*   | Type of profile for encoding. Currently Ingest supports `hls` and `mp4` |
| created_at      | *string*   | Date and time of creation                                               |
| updated_at      | *string*   | Date and time of last update                                            |
| deleted_at      | *string*   | Date and time of deletion                                               |
| data            | *object*   | Profile data. Depends on the `type` of profile.                         |
| data.playlists  | *[object]* | Variant playlists created from renditions.                              |
| data.renditions | *[object]* | Describes the various encoding settings to create a rendition.          |

## HLS Playlists

Schema for the HLS Playlist object:

| Attribute       | Type      | Description                                                                       |
| --------------- |:---------:| ---------------------------------------------------------------------------------:|
| name            | *string*  | A unique identifier to the variants, they have to be unique for a video resource. |
| byte_range      | *boolean* | Indicates if is segmented or use byte-range style HLS                             |
| iframe_playlist | *boolean* | Indicates use of iframe playlists in the renditions of this variant               |
| version         | *integer* | HLS version it targets                                                            |

## HLS Renditions

Schema for the HLS Rendition object:

| Attribute               | Type       | Description                                                                                   |
| ----------------------- |:----------:| ---------------------------------------------------------------------------------------------:|
| id                      | *integer*  | Number representing the rendition inside the JSON object for referencing inside the playlists |
| audio                   | *object*   | Encoding settings for audio specifically                                                      |
| audio.bitrate           | *string*   | Bitrate to use for audio encoding                                                             |
| audio.channels          | *integer*  | Number of audio channels, if omitted, use source number                                       |
| audio.codec             | *string*   | Codec to use for audio encoding (recommend libfdk_aac)                                        |
| audio.sample_rate       | *string*   | Set audio sample rate                                                                         |
| video                   | *object*   | Encoding settings for video specifically                                                      |
| video.bitrate           | *string*   | Bitrate to use for video encoding                                                             |
| video.codec             | *string*   | Codec to use for video encoding (recommend libx264)                                           |
| video.codec_options     | *object*   | Values to apply through directly to the encoder                                               |
| video.framerate         | *float*    | Framerate to use for the video                                                                |
| video.height            | *integer*  | Video height                                                                                  |
| video.keep_aspect_ratio | *boolean*  | If true, uses video width to choose height and keep the aspect ratio from the input.          |
| video.keyframe          | *integer*  | Number of frames of video between keyframes                                                   |
| video.profile           | *string*   | Profile to use for encoding (baseline, main, high)                                            |
| video.width             | *integer*  | Video width                                                                                   |
| streams                 | *[string]* | Which streams should be included in the HLS MPEGTS segments `(audio, video, captions)`        |
