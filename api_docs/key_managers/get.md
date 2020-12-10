# Show Accessible Key Managers

Show all Key Managers the active User can access and with what permission level. 

**URL** : `/key_managers/`

**Method** : `GET`

**Auth required** : Yes

**Permissions Required** : None

**Data constraints**

```json
{
}
```

## Success Response

**Code** : `200 OK`

**Response Body Example**

```json
{
    "key_managers": [
        {
            "key_manager": {
                "created_at": "2020-11-26T01:40:58.000+00:00",
                "updated_at": "2020-11-26T01:40:58.000+00:00",
                "description": "Synergistic object-oriented software",
                "email": "emma@buckridge.net",
                "employee_id": "GB47XPTZ71440716730125",
                "name": "Vernon Mertz",
                "organization_id": "a6d1a3ce-ab51-42d0-b824-90022777c4ad",
                "phone_number": "108-608-4483",
                "title": "Dynamic Planner",
                "user_id": "551bef65-5b38-4d78-b98f-42284afa27dc",
                "id": "4e053145-82b5-47ac-b1ea-b0c2e0134516"
            }
        },
        {
            "key_manager": {
                "created_at": "2020-11-26T01:40:58.000+00:00",
                "updated_at": "2020-11-26T01:40:58.000+00:00",
                "description": "Organized mission-critical secured line",
                "email": "virgil.skiles@mante.name",
                "employee_id": "GB69VMWZ18475430238521",
                "name": "Adriana McDermott",
                "organization_id": "a6d1a3ce-ab51-42d0-b824-90022777c4ad",
                "phone_number": "287-621-7367",
                "title": "Forward Engineer",
                "user_id": "551bef65-5b38-4d78-b98f-42284afa27dc",
                "id": "c7462083-bc4f-4b42-a7fc-5912898d4c37"
            }
        },
        {
            "key_manager": {
                "created_at": "2020-11-26T01:40:58.000+00:00",
                "updated_at": "2020-11-26T01:40:58.000+00:00",
                "description": "Reactive 4th generation encryption",
                "email": "enoch.jacobs@jones-ernser.biz",
                "employee_id": "GB30QFLD44659630935069",
                "name": "Mervin Reilly V",
                "organization_id": "a6d1a3ce-ab51-42d0-b824-90022777c4ad",
                "phone_number": "(592) 632-6894",
                "title": "Principal Banking Manager",
                "user_id": "551bef65-5b38-4d78-b98f-42284afa27dc",
                "id": "2d995619-c76a-460f-b4c3-5ec546cfef44"
            }
        }
    ]
}
```
