# Update Key Manager

Updates the Key Manager if the Authenticated User has permission.

**URL** : `/key_managers/:id/`

**Method** : `PUT`

**Auth required** : YES

**Permissions required** : YES

**Data constraints**

```json
{
     "key_manager": {
            "description": "[string]",
            "email": "[string]",
            "employee_id": "[string]",
            "name": "[string]",
            "organization_id": "[UUID]",
            "password": "[string]",
            "phone_number": "[string]",
            "title": "[string]"
        }
}
```

**Data example** Partial data is allowed.

```json
{
    "name": "Mervin Reilly",
}
```

## Success Responses

**Condition** : Update can be performed either fully or partially by the Owner
of the Organization.

**Code** : `200 OK`

**Content example** : For the example above, when the 'name' is updated and
posted to `/key_managers/3abe4145-7303-44c2-8831-c46d1c368e41/`...

```json

{
    "key_managers": {
        "key_manager": {
            "created_at": "2020-11-26T01:40:58.000+00:00",
            "updated_at": "2020-11-27T11:28:36.735-07:00",
            "description": "Reactive 4th generation encryption",
            "email": "enoch.jacobs@jones-ernser.biz",
            "employee_id": "GB30QFLD44659630935069",
            "name": "Tickles",
            "organization_id": "a6d1a3ce-ab51-42d0-b824-90022777c4ad",
            "phone_number": "(592) 632-6894",
            "title": "Principal Banking Manager",
            "user_id": "551bef65-5b38-4d78-b98f-42284afa27dc",
            "id": "2d995619-c76a-460f-b4c3-5ec546cfef44"
        }
    }
}

```

## Error Response

**Condition** : Key Manager does not exist

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

E.g. if Key Manager already exits:

**Data example**

```json
{
    "wibble": "flobble",
    "id": 987,
    "name" : "Giggles"
}
```

**Code** : `200 OK`

**Content example**

```json
{
    "id": 123,
    "name": "Giggles",
}
```