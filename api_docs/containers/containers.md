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
| `share_build_with_community` | Posts a version of your computer build to the community.  Options are `true` or `false` |
| `url_link` | The url link where the item can be found. |
| `uses_biometric_access_control` | Options are `true` or `false` |
| `uses_combination_lock` | Options are `true` or `false` |
| `uses_login_credentials_access_control` | Options are `true` or `false` |
| `uses_pin_tumbler_locks` | Options are `true` or `false` |
| `uses_tangible_device_access_control` | Options are `true` or `false` |
| `type` | The type of container. Options are `bag`, `safe`, `safe_deposit_box`, or `other`|

## Associations

| Associations | Node | Relationship |
| --- | --- | --- |
| `has_one` | `facility` | `stored_in` |
| `has_many` | `key_managers` | `access` |
| `has_many` | `key_storage_devices` | `stored_in` |
| `has_many` | `seed_backups` | `stored_in` |
| `has_many` | `entropy_sources` | `stored_in` |
| `has_one` | `location` | `located_at` |

## API endpoints

Endpoints for viewing and manipulating `containers` that the `user` has permissions to access. Requires a valid token to be included in the header of the request. A token can be acquired using [user login](../../api_docs/open/login.md) : `POST /user/sign_in`

<!-- * [Show Accessible Containers](api_docs/containers/get.md) : `GET /containers/`
* [Create A Container](api_docs/containers/post.md) : `POST /containers/`
* [Show A Container](api_docs/containers/id/get.md) : `GET /containers/:id/`
* [Update A Container](api_docs/containers/id/put.md) : `PUT /containers/:id/`
* [Delete A Container](api_docs/containers/id/delete.md) : `DELETE /containers/:id/` -->
