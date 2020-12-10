# Login

Used to collect a Bearer Token for a registered User.

**URL** : `/login/`

**Method** : `POST`

**Auth required** : NO

**Data constraints**

```json
{
    "username": "[valid email address]",
    "password": "[password in plain text]"
}
```

**Data example**

```json
{
    "username": "iloveauth@example.com",
    "password": "abcd1234"
}
```

## Success Response

**Code** : `200 OK`

**Response Header Example**

```json
{
    "Authorization": "Bearer 93144b288eb1fdccbe46d6fc0f241a51766ecd3d..."
}
```

**Response Body Example**

```json
{
"id": "66de69eb-434c-4eda-b914-d921beb18a55",
    "address1": null,
    "bio": "CEO FreeRange",
    "canHire": false,
    "cellPhone": null,
    "city": null,
    "country": null,
    "email": "demo@freeran.ge",
    "employer": null,
    "employee_id": null,
    "firstName": "Joseph",
    "is_active": true,
    "isPublic": true,
    "lastName": "Pitluck",
    "occupation": null,
    "organizaton": null,
    "organization_id": null,
    "phone": null,
    "policy": false,
    "role": null,
    "state": null,
    "title": null,
    "user_name": null,
    "zipcode": null,
    "created_at": "2020-11-13T18:05:22.076Z",
    "updated_at": "2020-11-13T18:05:22.176Z",
    "data": {},
    "avatar": "/rails/active_storage/blobs/eyJfcmFpbHMiOnsibWVzc2FnZSI6IkJBaEpJaWs0WW1ZelpUQXdPUzAyTWpCaExUUXlPR1F0T0dNNE15MHhOMlEzT0RoaE1EazJNRGNHT2daRlZBPT0iLCJleHAiOm51bGwsInB1ciI6ImJsb2JfaWQifX0=--9c410cea5ec259235fe664f721e35ccfd4c53820/avatar.png"
}
```

## Error Response

**Condition** : If 'username' and 'password' combination is wrong.

**Code** : `400 BAD REQUEST`

**Content** :

none