# Locations

- [Description](#description)
- [Properties](#properties)
- [Associations](#associations)
- [API endpoints](#api-endpoints)

## Description

Location parameters were designed to be agnostic regardless of jurisdiction. 
For example, documenting the location of a key storage device in Costa Rica would be difficult using 
a traditonal address schema, as many streets have no name and many buildngs do not have numbers assigned.

Latitude and Longitude are available parameters, along with fields such as `landmark` and `natural_feature`.
We tried to account for multiple methodologies when choosing a location for storing device and seed backups, from
bank locations where safe deposit boxes are located, to 
> *"A hole dug in the backyard behind the shed in a yard with a large fence and camera system." - Josh M.*

| Properties | Description |
| --- | --- |
| `administrative_area_level_1` | indicates a first-order civil entity below the country level. Within the United States, these administrative levels are states. Not all nations exhibit these administrative levels. In most cases, administrative_area_level_1 short names will closely match ISO 3166-2 subdivisions and other widely circulated lists; however this is not guaranteed as our geocoding results are based on a variety of signals and location data. |
| `administrative_area_level_2` | indicates a second-order civil entity below the country level. Within the United States, these administrative levels are counties. Not all nations exhibit these administrative levels. |
| `administrative_area_level_3` | indicates a third-order civil entity below the country level. This type indicates a minor civil division. Not all nations exhibit these administrative levels. |
| `administrative_area_level_4` | indicates a fourth-order civil entity below the country level. This type indicates a minor civil division. Not all nations exhibit these administrative levels. |
| `administrative_area_level_5` | indicates a fifth-order civil entity below the country level. This type indicates a minor civil division. Not all nations exhibit these administrative levels. |
| `border_color` | Used for the node's sprite border color. Rendered with ThreeJS/WebGl. |
| `background_color` | Used for the node's sprite color. Rendered with ThreeJS/WebGl. |
| `country` | indicates the national political entity. |
| `description` | A short description of the location. |
| `floor` | indicates the floor of a building address. |
| `intersection` | indicates a major intersection, usually of two major roads. |
| `landmark` | indicates a nearby place that is used as a reference, to aid navigation. |
| `lat` | Latitude in decimal format. |
| `locality` | indicates an incorporated city or town political entity. |
| `lng` | Longitude in decimal format. |
| `name` | indicates the name of the location |
| `natural_feature` | indicates a prominent natural feature. |
| `neighborhood` | indicates a named neighborhood. |
| `park` | indicates a named park. |
| `plus_code` | indicates an encoded location reference, derived from latitude and longitude. Plus codes can be used as a replacement for street addresses in places where they do not exist (where buildings are not numbered or streets are not named). See https://plus.codes for details. |
| `point_of_interest` | indicates a named point of interest. Typically, these "POI"s are prominent local entities that don`t easily fit in another category, such as "Empire State Building" or "Eiffel Tower". |
| `postal_code` | indicates a postal code as used to address postal mail within the country. |
| `postal_town` | indicates a grouping of geographic areas, such as locality and sublocality, used for mailing addresses in some countries. |
| `post_box` | indicates a specific postal box. |
| `premise` | indicates a named location, usually a building or collection of buildings with a common name. |
| `room` | indicates the room of a building address. |
| `risk_of_blast_damage` | indicates the risk of blast damage at this location over time, on a scale from 1-99, with `1` indicating the lowest risk and `99` indicating the highest risk. | 
| `risk_of_earthquake_damage` | indicates the risk of earthquake damage at this location over time, on a scale from 1-99, with `1` indicating the lowest risk and `99` indicating the highest risk. | 
| `risk_of_emp_damage` | indicates the risk of electromagnetic pulse damage at this location over time, on a scale from 1-99, with `1` indicating the lowest risk and `99` indicating the highest risk. | 
| `risk_of_fire_damage` | indicates the risk of fire damage at this location over time, on a scale from 1-99, with `1` indicating the lowest risk and `99` indicating the highest risk. | 
| `risk_of_flood_damage` | indicates the risk of flood damage at this location over time, on a scale from 1-99, with `1` indicating the lowest risk and `99` indicating the highest risk. | 
| `risk_of_jurisdiction` | indicates the risk of jurisdictional instability at this location over time, on a scale from 1-99, with `1` indicating the lowest risk and `99` indicating the highest risk. | 
| `risk_of_heat_damage` | indicates the risk of heat damage at this location over time, on a scale from 1-99, with `1` indicating the lowest risk and `99` indicating the highest risk. | 
| `risk_of_hurricane_damage` | indicates the risk of hurricane damage at this location over time, on a scale from 1-99, with `1` indicating the lowest risk and `99` indicating the highest risk. | 
| `risk_of_tornado_damage` | indicates the risk of tornado damage at this location over time, on a scale from 1-99, with `1` indicating the lowest risk and `99` indicating the highest risk. | 
| `route` | indicates a named route (such as "US 101"). |
| `street_address` | indicates a precise street address. |
| `street_number` | indicates the precise street number. |
| `subpremise` | indicates a first-order entity below a named location, usually a singular building within a collection of buildings with a common name. |
| `type` | indicates the location type. ***Options still need to be created*** |

| Associations | Node | Relationship |
| --- | --- | --- |
| `has_many` | `facilities` | `located_at` |
| `has_many` | `computers` | `located_at` |
| `has_many` | `containers` | `located_at` |
| `has_many` | `entropy_sources` | `located_at` |
| `has_many` | `key_ceremonies` | `located_at` |
| `has_many` | `key_managers` | `located_at` |
| `has_many` | `key_storage_devices` | `located_at` |
| `has_many` | `organizations` | `located_at` |
| `has_many` | `rooms` | `located_at` |
| `has_many` | `seed_backups` | `located_at` |

Endpoints for viewing and manipulating the Accounts that the Authenticated User
has permissions to access.

* [Show Accessible Locations](api_docs/locations/get.md) : `GET /locations/`
* [Create A Location](api_docs/locations/post.md) : `POST /locations/`
* [Show A Location](api_docs/locations/id/get.md) : `GET /locations/:id/`
* [Update A Location](api_docs/locations/id/put.md) : `PUT /locations/:id/`
* [Delete A Location](api_docs/locations/id/delete.md) : `DELETE /locations/:id/`