# Show Accessible Key Storage Devices

Show all Key Storage Devices the active User can access and with what permission level.

**URL** : `/key_managers/`

**Method** : `GET`

**Auth required** : Yes

**Permissions Required** : None

**Data constraints**

```json
{}
```

## Success Response

**Code** : `200 OK`

**Response Body Example**

```json
{
  "key_storage_devices": [
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
    },
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
    },
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
        "id": "ba8aca69-15d0-4c3e-89dd-5bcece499f0d"
      }
    }
  ]
}
```
