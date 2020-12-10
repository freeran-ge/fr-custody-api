# Delete Organization

Delete the Organization of the Authenticated User if they are Owner.

**URL** : `/organizations/:id/`

**URL Parameters** : `id=[string]` where `id` is the ID of the Organization in the
database.

**Method** : `DELETE`

**Auth required** : YES

**Permissions required** : User is Organization Owner

**Data** : `{}`

## Success Response

**Condition** : If the Organization exists.

**Code** : `200 OK`

**Content** : `{}`

## Error Responses

**Condition** : If there was no Organization available to delete.

**Code** : `404 NOT FOUND`

**Content** : `{}`

### Or

**Condition** : Authorized User is not Owner of Organization at URL.

**Code** : `401 UNAUTHORZED`

**Content** 

```json
{
    "error": "UNAUTHORIZED"
}
```


## Notes

* Not sure what this does yet to everything that was attached to the organization.