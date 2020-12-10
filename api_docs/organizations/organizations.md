# Organizations

- [Description](#description)
- [Properties table](#properties-table)
- [Associations table](#associations-table)
- [API endpoints](#api-endpoints)

## Description

`organizations` comprise of `key_managers` collectively managing digital assets and/or their respective cryptographic public / private key pairings.

## Properties table

| Properties | Description |
| --- | --- |
| `background_color` | Used for the node's sprite color. Rendered with ThreeJS/WebGl. |
| `border_color` | Used for the node's sprite border color. Rendered with ThreeJS/WebGl. |
| `contact_name` | The name of the primary contact person of the organization. |
| `contact_title` | The title of the primary contact person of the organization. |
| `contact_phone` | The phone number of the primary contact person of the organization. |
| `description` | A short descrption of the organization. |
| `email` | The primary contact email of the organization. |
| `entity_type` | The organization type. Types can be: `bank`, `company`, `family_office` `foundation`, `trust_company`, `other`  |

## Associations table

| Associations | Node | Relationship |
| --- | --- | --- |
| `has_many` | `accounts` | `belongs_to` |
| `has_many` | `facilities` | `belongs_to` |
| `has_many` | `computers` | `belongs_to` |
| `has_many` | `containers` | `belongs_to` |
| `has_many` | `entropy_sources` | `belongs_to` |
| `has_many` | `key_managers` | `belongs_to` |
| `has_many` | `key_storage_devices` | `belongs_to` |
| `has_many` | `locations` | `located_at` |
| `has_many` | `rooms` | `belongs_to` |

## API endpoints

Endpoints for viewing and manipulating the `organizations` that the `user` has permissions to access.

* [Show accessible organizations](get.md) : `GET /organizations/`
* [Create an organization](post.md) : `POST /organizations/`
* [Show an organization](id/get.md) : `GET /organizations/:id/`
* [Show an organization's relationships](id/graph_data/get.md) : `GET /organizations/:id/graph_data`
* [Update an organization](id/put.md) : `PUT /organizations/:id/`
* [Delete an organization](id/delete.md) : `DELETE /organizations/:id/`