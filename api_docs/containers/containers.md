# Containers

- [Description](#description)
- [Properties](#properties)
- [Associations](#associations)
- [API endpoints](#api-endpoints)

## Description

A physical object used for storing and securing items such as `key_storage_devices`. An example would be a safe deposit box or Faraday bag. Multiple types of `containers` can be nested within each other.

## Properties

| Properties | Description |
| --- | --- |
| `description` | A short description of the container. |
| `name` | The name of the container. |
| `resistance_to_blast` | Indicates the resistance to blast damage on a scale from 1-99, with `1` offering no protective resistance to blast damage, and `99` offering the highest level of resistance to blast damage. |
| `resistance_to_emp` | Indicates the resistance to electromagnetic pulse (EMP) damage on a scale from 1-99, with `1` offering no protective resistance to EMP damage, and `99` offering the highest level of resistance to EMP damage. |
| `resistance_to_fire` | Indicates the resistance to fire damage on a scale from 1-99, with `1` offering no protective resistance to fire damage, and `99` offering the highest level of resistance to fire damage. |
| `resistance_to_flood` | Indicates the resistance to flood damage on a scale from 1-99, with `1` offering no protective resistance to damage, and `99` offering the highest level of resistance to flood damage. |
| `resistance_to_forceable_attack` | Indicates the resistance to penetrative forceable attack on a scale from 1-99, with `1` offering no protective resistance to penetrative forceable attack, and `99` offering the highest level of resistance to penetrative forceable attack. |
| `resistance_to_heat` | Indicates the resistance to heat damage on a scale from 1-99, with `1` offering no protective resistance to heat damage, and `99` offering the highest level of resistance to heat damage. |
| `type` | The type of container. ***Options still need to be defined*** |

| Associations | Node | Relationship |
| --- | --- | --- |
| `has_one` | `facility` | `stored_in` |
| `has_many` | `key_managers` | `access` |
| `has_many` | `key_storage_devices` | `stored_in` |
| `has_many` | `seed_backups` | `stored_in` |
| `has_many` | `entropy_sources` | `stored_in` |
| `has_one` | `location` | `located_at` |

## API endpoints

Endpoints for viewing and manipulating the Accounts that the Authenticated User
has permissions to access.

* [Show Accessible Containers](api_docs/containers/get.md) : `GET /containers/`
* [Create A Container](api_docs/containers/post.md) : `POST /containers/`
* [Show A Container](api_docs/containers/id/get.md) : `GET /containers/:id/`
* [Update A Container](api_docs/containers/id/put.md) : `PUT /containers/:id/`
* [Delete A Container](api_docs/containers/id/delete.md) : `DELETE /containers/:id/`