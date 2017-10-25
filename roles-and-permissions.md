# Ingest Roles & Permissions

User permissions are grouped into sets of roles. There are two default roles: Default Admin Role (for network admins), and Default User Role (for new users added to the network). Other roles can be setup to customize user permissions into any combination.

The expected format for the permissions object is:

| Attribute   | Type     | Description                                                |
| ----------- |:--------:| ----------------------------------------------------------:|
| action      | *string* | Represents action of scope (read, write)                   |
| resource    | *string* | Represents resource scope action refers to (videos, users) |
