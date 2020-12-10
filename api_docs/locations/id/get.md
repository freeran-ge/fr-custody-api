# Show a Single Location

Show a single Location if current the User has access permissions to it.

**URL** : `/locations/:id/`

**URL Parameters** : `id=[string]` where `id` is the ID of the Location on the
server.

**Method** : `GET`

**Auth required** : YES

**Permissions required** : YES

**Data**: `{}`

## Success Response

**Condition** : If the Location exists and the Authorized User has required permissions.

**Code** : `200 OK`

**Content example**

```json
{
  "location": {
    "created_at": "2020-12-04T18:04:52.000+00:00",
    "updated_at": "2020-12-04T18:04:52.000+00:00",
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
    "name": "The Office",
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

## Error Responses

**Condition** : If Location does not exist with `id` of provided `id` parameter.

**Code** : `404 NOT FOUND`

**Content** : `{}`

### Or

**Condition** : If Location exists but the Authorized User does not have required
permissions.

**Code** : `401 UNAUTHORIZED`

**Content** :

```json
{ "error": "Unauthorized" }
```

## Notes

There are security issues:

- This view allows existing users to test for existence of Locations that exist
  but that they do not have access to.
- In the development enviroment, the 404 content is very verbose. Must check to see if this is true in production.
