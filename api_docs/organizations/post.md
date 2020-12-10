# Create Organization

Create an Organization for the authenticated User if an Organization for that User does
not already exist. Each User can have many Organizations.

**URL** : `/organizations/`

**Method** : `POST`

**Auth required** : YES

**Permissions required** : None

**Data constraints**

Partial data is allowed, but the name of the Organization must be provided to be created.

```json
{
    "organization": {
                "border_color": "#008000",
                "background_color": "#008000",
                "contact_name": "[string]",
                "contact_title": "[string]",
                "contact_phone": "[string]",
                "description": "[string]",
                "email": "[string]",
                "entity_type": "[Must be 'bank', 'company', 'family_office, 'foundation', 'trust_company', 'other' ]",
                "name": "[string]"
    }
}
```

**Data example** Name field must be sent.

```json
{
    "name": "Super Friends Department"
}
```

## Success Response

**Condition** : If everything is OK.

**Code** : `200 OK`

**Content example**

```json
{
    "organization": {
        "organization": {
            "created_at": "2020-11-26T00:25:34.000+00:00",
            "updated_at": "2020-11-26T00:25:34.000+00:00",
            "background_color": "#008000",
            "border_color": "#008000",
            "contact_name": null,
            "contact_title": null,
            "contact_phone": null,
            "email": null,
            "entity_type": null,
            "name": "Super Friends",
            "user_id": "6491857b-ef71-487c-ba77-403ac802a32f",
            "id": "4bb9f3f0-3e44-4cb1-8eaa-7a8f3e60c21c"
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