# Create Key Storage Device

Creates a Key Storage Device for the Authenticated User. Each User can have many Key Storage Devices.

**URL** : `/key_storage_device/`

**Method** : `POST`

**Auth required** : YES

**Permissions required** : None

**Data constraints**

Partial data is allowed, but the name and Organization id of the Key Storage Device must be provided to be created.

```json
{
     "key_storage_device": {
            "description": "[string]",
            "name": "[string]",
            "organization_id": "[string]"
}
```

**Data example** Name and Organization id field must be sent.

```json
{
  "name": "Marvin Tipper",
  "organization_id": "9f8fe15a-fdcf-498a-904e-b70260d0b499"
}
```

## Success Response

**Condition** : If everything is OK.

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
    "id": "17306760-1ec8-48d5-9c18-e61d8538be03"
  }
}
```

## Error Responses

<!-- **Condition** : If Organization already exists for User.

**Code** : `303 SEE OTHER`

**Headers** : `Location: http://testserver/api/Organizations/123/`

**Content** : `{}`

### Or -->

**Condition** : If name or organization id field is missing.

**Code** : `400 BAD REQUEST`

**Content example**

```json
{
  "error": "BAD REQUEST"
}
```
