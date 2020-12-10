# Create an Location

Creates an Location for the Authenticated User. Each User can have many Locations which are managed by User created Organizations.

**URL** : `/locations/`

**Method** : `POST`

**Auth required** : YES

**Permissions required** : None

**Data constraints**

Partial data is allowed, but Location `name` must be provided to be created.

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
    "type": "[string]",
  }
}
```
**Data fields overview**

The data model for Locations was derived from  
[Google Geocoding API Overview](https://developers.google.com/maps/documentation/geocoding/overview#Types).

Location parameters were designed to be agnostic regardless of jurisdiction. 
For example, documenting the location of a key storage device in Costa Rica would be difficult using 
a traditonal address schema, as many streets have no name and many buildngs do not have numbers assigned.

Latitude and Longitude are available parameters, along with fields such as `landmark` and `natural_feature`.
We tried to account for multiple methodologies when choosing a location for storing device and seed backups, from
bank locations where safe deposit boxes are located, to under that large rock 200 feet from the bend of the river.

- `street_address` indicates a precise street address.
- `route` indicates a named route (such as "US 101").
- `intersection` indicates a major intersection, usually of two major roads.
- `country` indicates the national political entity, and is typically the highest order type returned by the Geocoder.
- `administrative_area_level_1` indicates a first-order civil entity below the country level. Within the United States, these administrative levels are states. Not all nations exhibit these administrative levels. In most cases, administrative_area_level_1 short names will closely match ISO 3166-2 subdivisions and other widely circulated lists; however this is not guaranteed as our geocoding results are based on a variety of signals and location data.
- `administrative_area_level_2` indicates a second-order civil entity below the country level. Within the United States, these administrative levels are counties. Not all nations exhibit these administrative levels.
- `administrative_area_level_3` indicates a third-order civil entity below the country level. This type indicates a minor civil division. Not all nations exhibit these administrative levels.
- `administrative_area_level_4` indicates a fourth-order civil entity below the country level. This type indicates a minor civil division. Not all nations exhibit these administrative levels.
- `administrative_area_level_5` indicates a fifth-order civil entity below the country level. This type indicates a minor civil division. Not all nations exhibit these administrative levels.
- `lat` Latitude in decimal format 
- `locality` indicates an incorporated city or town political entity.
- `lng` Longitude in decimal format 
- `neighborhood` indicates a named neighborhood
- `premise` indicates a named location, usually a building or collection of buildings with a common name
- `subpremise` indicates a first-order entity below a named location, usually a singular building within a collection of buildings with a common name
- `plus_code` indicates an encoded location reference, derived from latitude and longitude. Plus codes can be used as a replacement for street addresses in places where they do not exist (where buildings are not numbered or streets are not named). See https://plus.codes for details.
- `postal_code` indicates a postal code as used to address postal mail within the country.
- `natural_feature` indicates a prominent natural feature.
- `park` indicates a named park.
- `point_of_interest` indicates a named point of interest. Typically, these "POI"s are prominent local entities that don`t easily fit in another category, such as "Empire State Building" or "Eiffel Tower".


**Data example** Fields below show the minimal data fields required.
```json
{
  "location": {
    "name": "The Office"
  }
}
```

## Success Response

**Condition** : If everything is OK.

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
