# Supported Events

| Name                     | Description                                                    |
|------------------------- | ---------------------------------------------------------------|
| users.delete             | Whenever a user is temporarily or permanently deleted          |
| videos.create            | Whenever a new video is created                                |
| videos.update            | Whenever a video is updated                                    |
| videos.delete            | Whenever a video is temporarily or permanently deleted         |
| videos.thumbnails.create | Whenever a new video thumbnail is uploaded                     |
| videos.thumbnails.delete | Whenever a video thumbnail is deleted                          |
| inputs.create            | Whenever an input resource is created                          |
| inputs.complete          | Whenever an input has been processed and is ready for encoding |
| inputs.update            | Whenever an input resource is updated                          |
| inputs.delete            | Whenever an input is deleted                                   |
| inputs.cancelled         | Whenever an input upload is cancelled                          |
| jobs.create              | Whenever an encoding job is created                            |
| jobs.error               | Whenever an encoding job fails                                 |
| jobs.complete            | Whenever an encoding job is complete                           |
| networks.update          | Whenever a network resource is updated                         |
| networks.update_status   | Whenever a network `read_only` status is updated               |
| networks.users.create    | Whenever a user is added to a network                          |
| networks.users.delete    | Whenever a user is removed from a network                      |
| networks.keys.create     | Whenever a network key is created                              |
| networks.keys.update     | Whenever a network key is updated                              |
| networks.keys.delete     | Whenever a network key is deleted                              |
| profiles.create          | Whenever an encoding profile is created                        |
| profiles.update          | Whenever an encoding profile is updated                        |
| profiles.delete          | Whenever an encoding profile is deleted                        |
| roles.create             | Whenever a role is created                                     |
| roles.update             | Whenever a role is updated                                     |
| roles.delete             | Whenever a role is deleted                                     |
