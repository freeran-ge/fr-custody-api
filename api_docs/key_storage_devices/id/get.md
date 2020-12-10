# Show a Single Key Storage Device

Show a single Key Storage Device if current User has access permissions to it.

**URL** : `/key_storage_device/:id/`

**URL Parameters** : `id=[string]` where `id` is the ID of the Key Storage Device on the
server.

**Method** : `GET`

**Auth required** : YES

**Permissions required** :

**Data**: `{}`

## Success Response

**Condition** : If the Key Storage Device exists and Authorized User has required permissions.

**Code** : `200 OK`

**Content example**

```json
{
  "key_storage_device": {
    "created_at": "2020-12-03T22:56:29.000+00:00",
    "updated_at": "2020-12-03T22:56:29.000+00:00",
    "border_color": "#008000",
    "background_color": "#0747A6",
    "description": null,
    "name": "Trezor Model T",
    "organization_id": "9f8fe15a-fdcf-498a-904e-b70260d0b499",
    "user_id": "70f492ef-e493-4400-bd51-9f80bbf4e907",
    "id": "1cab21fa-a921-44af-9c71-ea08a7c12c5a"
  }
}
```

## Error Responses

**Condition** : If Key Storage Device does not exist with `id` of provided `id` parameter.

**Code** : `404 NOT FOUND` 

**Content** : `{}`

### Or

**Condition** : If Key Storage Device exists but the Authorized User does not have required
permissions.

**Code** : `401 UNAUTHORIZED`

**Content** :

```json
{ "error": "Unauthorized" }
```

## Notes

There are security issues:

- This view allows existing users to test for existence of Key Storage Devices that exist
  but that they do not have access to.
- In the development enviroment, the 404 content is very verbose. Must check to see if this is true in production.
