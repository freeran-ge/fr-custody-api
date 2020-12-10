# Create Key Manager

Creates a Key Manager for the Authenticated User if a Key Manager for that User does
not already exist. Each User can have many Key Managers.

**URL** : `/key_manager/`

**Method** : `POST`

**Auth required** : YES

**Permissions required** : None

**Data constraints**

Partial data is allowed, but the name of the Key Manager must be provided to be created.

```json
{
     "key_manager": {
            "description": "[string]",
            "email": "[string]",
            "employee_id": "[string]",
            "name": "[string]",
            "password": "[string]",
            "phone_number": "[string]",
            "title": "[string]"
        }
}
```

**Data example** Name field must be sent.

```json
{
    "name": "Marvin Tipper"
}
```

## Success Response

**Condition** : If everything is OK.

**Code** : `200 OK`

**Content example**

```json
{
    "key_managers": {
        "key_manager": {
            "created_at": "2020-11-27T18:19:37.000+00:00",
            "updated_at": "2020-11-27T18:19:37.000+00:00",
            "description": null,
            "email": null,
            "employee_id": null,
            "name": "Super Friend",
            "organization_id": null,
            "phone_number": null,
            "title": null,
            "user_id": "551bef65-5b38-4d78-b98f-42284afa27dc",
            "id": "5ac3d0f6-b2af-417d-b7c7-15edd8d350c0"
        }
    }
}
```

## Error Responses

<!-- **Condition** : If Organization already exists for User.

**Code** : `303 SEE OTHER`

**Headers** : `Location: http://testserver/api/Organizations/123/`

**Content** : `{}`

### Or -->

**Condition** : If name field is missing.

**Code** : `400 BAD REQUEST`

**Content example**

```json
{
    "error": "BAD REQUEST"
}
```