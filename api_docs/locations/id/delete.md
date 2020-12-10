# Delete Location

Deletes the Location if the Authorized User has permission

**URL** : `/location/:id/`

**URL Parameters** : `id=[string]` where `id` is the ID of the Location in the
database.

**Method** : `DELETE`

**Auth required** : YES

**Permissions required** : Authenticated User must have permission to delete the Location

**Data** : `{}`

## Success Response

**Condition** : If the Location exists.

**Code** : `200 OK`

**Content** : `{}`

## Error Responses

**Condition** : If there was no Location available to delete.

**Code** : `404 NOT FOUND`

**Content** : `{}`

### Or

**Condition** : The Authorized User does not have permission to delete the Location.

**Code** : `401 UNAUTHORZED`

**Content** 

```json
{
    "error": "UNAUTHORIZED"
}
```
