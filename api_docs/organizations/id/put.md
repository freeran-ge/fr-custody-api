# Update Organization

Update the Organization of the Authenticated User if and only if they are Owner.

**URL** : `/Organizations/:id/`

**Method** : `PUT`

**Auth required** : YES

**Permissions required** : User is Organization Owner

**Data constraints**

```json
{
  "organization": {
    "border_color": "#008000",
    "background_color": "#008000",
    "contact_name": "[string]",
    "contact_title": "[string]",
    "contact_phone": "[string]",
    "email": "[string]",
    "entity_type": "Must be ['bank', 'company', 'family_office, 'foundation', 'trust_company', 'other' ]",
    "name": "[string]"
  }
}
```

**Data example** Partial data is allowed.

```json
{
  "name": "Acme Company"
}
```

## Success Responses

**Condition** : Update can be performed either fully or partially by the Owner
of the Organization.

**Code** : `200 OK`

**Content example** : For the example above, when the 'name' is updated and
posted to `/organizations/3abe4145-7303-44c2-8831-c46d1c368e41/`...

```json
{
  "organization": {
    "organization": {
      "created_at": "2020-11-25T19:21:39.000+00:00",
      "updated_at": "2020-11-25T23:34:58.000+00:00",
      "border_color": "#008000",
      "background_color": "#008000",
      "contact_name": null,
      "contact_title": null,
      "contact_phone": null,
      "email": "amber@fr.financial",
      "entity_type": "company",
      "name": "Fedddy",
      "user_id": "6491857b-ef71-487c-ba77-403ac802a32f",
      "id": "3abe4145-7303-44c2-8831-c46d1c368e41"
    }
  }
}
```

## Error Response

**Condition** : Organization does not exist at URL

**Code** : `404 NOT FOUND`

**Content** : `{}`

### Or

**Condition** : Authorized User is not Owner of Organization at URL.

**Code** : `401 Unauthorized`

**Content** : `"error": "UNAUTHORIZED"`

## Notes

### Data ignored

Endpoint will ignore irrelevant and read-only data such as parameters that
don't exist, or `id` and `parent_organization_id` fields which are not editable.

E.g. if Organization already exits:

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
