# Show a Single Key Manager

Show a single Key Manager if current User has access permissions to it.

**URL** : `/key_managers/:id/`

**URL Parameters** : `id=[string]` where `id` is the ID of the Key Manager on the
server.

**Method** : `GET`

**Auth required** : YES

**Permissions required** :

**Data**: `{}`

## Success Response

**Condition** : If the Key Manager exists and Authorized User has required permissions.

**Code** : `200 OK`

**Content example**

```json
{
    "key_managers": {
        "key_manager": {
            "created_at": "2020-11-26T01:40:58.000+00:00",
            "updated_at": "2020-11-26T01:40:58.000+00:00",
            "description": "Reactive 4th generation encryption",
            "email": "enoch.jacobs@jones-ernser.biz",
            "employee_id": "GB30QFLD44659630935069",
            "name": "Mervin Reilly V",
            "Key Manager_id": "a6d1a3ce-ab51-42d0-b824-90022777c4ad",
            "phone_number": "(592) 632-6894",
            "title": "Principal Banking Manager",
            "user_id": "551bef65-5b38-4d78-b98f-42284afa27dc",
            "id": "2d995619-c76a-460f-b4c3-5ec546cfef44"
        }
    }
}
```

## Error Responses

**Condition** : If Key Manager does not exist with `id` of provided `id` parameter.

**Code** : `404 NOT FOUND`

**Content** : `{}`


### Or

**Condition** : If Key Manager exists but the Authorized User does not have required
permissions.

**Code** : `401 UNAUTHORIZED`

**Content** :

```json
{"error": "Unauthorized"}
```

## Notes

There are security issues:

* This view allows existing users to test for existence of Key Managers that exist
    but that they do not have access to.
* In the development enviroment, the 404 content is very verbose. Must check to see  if this is true in production.
