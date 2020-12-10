# Delete Key Manager

Deletes the Key Manager if the Authorized User has permission

**URL** : `/key_manager/:id/`

**URL Parameters** : `id=[string]` where `id` is the ID of the Key Manager in the
database.

**Method** : `DELETE`

**Auth required** : YES

**Permissions required** : Authorized User must have permission to delete the Key Manager

**Data** : `{}`

## Success Response

**Condition** : If the Key Manager exists.

**Code** : `200 OK`

**Content** : `{}`

## Error Responses

**Condition** : If there was no Key Manager available to delete.

**Code** : `404 NOT FOUND`

**Content** : `{}`

### Or

**Condition** : The Authorized User does not have permission to delete the Key Manager.

**Code** : `401 UNAUTHORZED`

**Content** 

```json
{
    "error": "UNAUTHORIZED"
}
```


## Notes

* Not sure what this does yet to everything that was attached to the Key Manager.