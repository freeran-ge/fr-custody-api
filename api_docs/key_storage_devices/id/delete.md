# Delete Key Storage Device

Deletes the Key Storage Device if the Authorized User has permission

**URL** : `/key_storage_devices/:id/`

**URL Parameters** : `id=[string]` where `id` is the ID of the Key Storage Device in the
database.

**Method** : `DELETE`

**Auth required** : YES

**Permissions required** : Authorized User must have permission to delete the Key Storage Device

**Data** : `{}`

## Success Response

**Condition** : If the Key Storage Device exists.

**Code** : `200 OK`

**Content** : `{}`

## Error Responses

**Condition** : If there was no Key Storage Device available to delete.

**Code** : `404 NOT FOUND`

**Content** : `{}`

### Or

**Condition** : The Authorized User does not have permission to delete the Key Storage Device.

**Code** : `401 UNAUTHORZED`

**Content** 

```json
{
    "error": "UNAUTHORIZED"
}
```


## Notes

* Not sure what this does yet to everything that was attached to the Key Storage Device.