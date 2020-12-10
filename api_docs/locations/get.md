# Show Accessible Locations

Show all Locations the active User can access.

**URL** : `/locations/`

**Method** : `GET`

**Auth required** : Yes

**Permissions Required** : None

**Data constraints**

```json
{}
```

## Success Response

**Code** : `200 OK`

**Response Body Example**

```json
{
  "locations": [
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
  ]
}
```
