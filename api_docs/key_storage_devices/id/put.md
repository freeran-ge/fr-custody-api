# Update Key Storage Device

Updates the Key Storage Device if the Authenticated User has permission.

**URL** : `/key_storage_device/:id/`

**Method** : `PUT`

**Auth required** : YES

**Permissions required** : YES

**Data constraints**

```json
{
  "key_storage_device": {
    "description": "[string]",
    "name": "[string]",
    "organization_id": "[UUID]"
  }
}
```

**Data example** Partial data is allowed.

```json
{
  "name": "Mervin Reilly"
}
```

## Success Responses

**Condition** : Update can be performed either fully or partially by the Owner
of the Organization.

**Code** : `200 OK`

**Content example** : For the example above, when the 'name' is updated and
posted to `/key_storage_device/1cab21fa-a921-44af-9c71-ea08a7c12c5a/`...

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

## Error Response

**Condition** : Key Storage Device does not exist

**Code** : `404 NOT FOUND`

**Content** : `{}`

### Or

**Condition** : Authenticated User does not have permission.

**Code** : `401 Unauthorized`

**Content** : `"error": "UNAUTHORIZED"`

## Notes

### Data ignored

Endpoint will ignore irrelevant and read-only data such as parameters that
don't exist, or `id` fields which are not editable.

E.g. if Key Storage Device already exits:

**Data example**

```json
{
  "wibble": "flobble",
  "id": 987,
  "name": "Giggles"
}
```

**Code** : `200 OK`

**Content example**

```json
{
  "id": 123,
  "name": "Giggles"
}
```
