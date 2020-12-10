# Delete Account

Deletes the Account if the Authorized User has permission

**URL** : `/account/:id/`

**URL Parameters** : `id=[string]` where `id` is the ID of the Account in the
database.

**Method** : `DELETE`

**Auth required** : YES

**Permissions required** : Authenticated User must have permission to delete the Account

**Data** : `{}`

## Success Response

**Condition** : If the Account exists.

**Code** : `200 OK`

**Content** : `{}`

## Error Responses

**Condition** : If there was no Account available to delete.

**Code** : `404 NOT FOUND`

**Content** : `{}`

### Or

**Condition** : The Authorized User does not have permission to delete the Account.

**Code** : `401 UNAUTHORZED`

**Content** 

```json
{
    "error": "UNAUTHORIZED"
}
```


## Notes

* Not sure what this does yet to everything that was attached to the Account.