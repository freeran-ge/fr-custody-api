# Show Accessible Organizations

Show all Organizations the active User can access and with what permission level. Includes their own Organization if they have one.

**URL** : `/organizations/`

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
    "organizations": [
        {
            "organization": {
                "created_at": "2020-11-25T19:21:39.000+00:00",
                "updated_at": "2020-11-25T19:21:39.000+00:00",
                "border_color": "#008000",
                "background_color": "#008000",
                "contact_name": null,
                "contact_title": null,
                "contact_phone": null,
                "email": "amber@fr.financial",
                "entity_type": "company",
                "name": "Runolfsson Group",
                "user_id": "6491857b-ef71-487c-ba77-403ac802a32f",
                "id": "3abe4145-7303-44c2-8831-c46d1c368e41"
            }
        }
    ]
}
```
<!-- 

## Error Response

**Condition** : If 'username' and 'password' combination is wrong.

**Code** : `400 BAD REQUEST`

**Content** :

none -->