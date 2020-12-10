# Update Location

Updates the Location if the Authenticated User has permission.

**URL** : `/locations/:id/`

**Method** : `PUT`

**Auth required** : YES

**Permissions required** : YES

**Data constraints**

```json
{
  "location": {
    "administrative_area_level_1": "[string]",
    "administrative_area_level_2": "[string]",
    "administrative_area_level_3": "[string]",
    "administrative_area_level_4": "[string]",
    "administrative_area_level_5": "[string]",
    "border_color": "[string]",
    "background_color": "[string]",
    "country": "[string]",
    "description": "[string]",
    "floor": "[string]",
    "intersection": "[string]",
    "landmark": "[string]",
    "lat": "[number]",
    "locality": "[string]",
    "lng": "[number]",
    "name": "[string]",
    "natural_feature": "[string]",
    "neighborhood": "[string]",
    "park": "[string]",
    "plus_code": "[string]",
    "point_of_interest": "[string]",
    "postal_code": "[string]",
    "postal_town": "[string]",
    "post_box": "[string]",
    "premise": "[string]",
    "room": "[string]",
    "route": "[string]",
    "street_number": "[string]",
    "street_address": "[string]",
    "subpremise": "[string]",
    "type": "[string]"
  }
}
```

**Data example** Partial data is allowed.

```json
{
  "location": {
    "name": "A Bigger Office"
  }
}
```

## Success Responses

**Condition** : Update can be performed either fully or partially by Authorized User.

**Code** : `200 OK`

**Content example** : For the example above, when the 'name' is updated and
posted to `952b5ec6-4193-4f5a-a95d-8f9b6d7740fd`...

```json
{
  "location": {
    "created_at": "2020-12-04T18:04:52.000+00:00",
    "updated_at": "2020-12-04T18:26:50.000+00:00",
    "administrative_area_level_1": null,
    "administrative_area_level_2": null,
    "administrative_area_level_3": null,
    "administrative_area_level_4": null,
    "administrative_area_level_5": null,
    "border_color": "#008000",
    "background_color": "#0747A6",
    "country": null,
    "description": null,
    "floor": null,
    "intersection": null,
    "landmark": null,
    "lat": null,
    "locality": null,
    "lng": null,
    "name": "A Bigger Office",
    "natural_feature": null,
    "neighborhood": null,
    "park": null,
    "plus_code": null,
    "point_of_interest": null,
    "postal_code": null,
    "postal_town": null,
    "post_box": null,
    "premise": null,
    "room": null,
    "route": null,
    "street_number": null,
    "subpremise": null,
    "type": null,
    "user_id": "e516db05-d533-4bd8-a076-0a7b3f278751",
    "id": "952b5ec6-4193-4f5a-a95d-8f9b6d7740fd"
  }
}
```

## Error Response

**Condition** : Location does not exist

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

E.g. if Location already exits:

**Data example**

```json
{
  "wibble": "flobble",
  "id": 987,
  "name": "A Bigger Office"
}
```

**Code** : `200 OK`

**Content example**

```json
{
  "id": 123,
  "name": "A Bigger Office"
}
```
