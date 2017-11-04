# Count Jobs

Returns the number of jobs in the authorized network. The response is returned in the form of a `Resource-Count` header.

**URL** : `/encoding/jobs`

**Method** : `HEAD`

**Auth required** : YES

**Permissions required** : `read_jobs`

## Success Response

**Code** : `204 OK`

**Response examples**

For jobs counted in the authorized network. The following header is returned

```json
Resource-Count: 20
```