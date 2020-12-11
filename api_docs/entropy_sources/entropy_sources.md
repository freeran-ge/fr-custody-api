# Entropy sources

- [Description](#description)
- [Properties](#properties)
- [Associations](#associations)
- [API endpoints](#api-endpoints)

## Description

Software, hardware, or analog derived (ex. deck of cards) randomness used in generating keys during `key_ceremonies`

## Properties

| Properties | Description |
| --- | --- |
| `description` | A short description of the entropy source. |
| `name` | The name of the entropy source. |
| `share_build_with_community` | Posts a version of your entropy source build to the community.  Options are `true` or `false` |
| `type` | The type of entropy source. Options include `cards`, `dice`, `trng` (true random number generator), or `other` |
| `url_link` | The url link where the item can be found. |

## Associations

| Associations | Node | Relationship |
| --- | --- | --- |
| `has_one` | `facility` | `stored_in` |
| `has_one` | `container` | `stored_in` |
| `has_many` | `key_ceremonies` | `used_in` |
| `has_many` | `key_managers` | `access` |
| `has_one` | `location` | `located_at` |

## API endpoints

Endpoints for viewing and manipulating the `entropy_sources` that the `user`
has permissions to access. Requires a valid token to be included in the header of the request. A token can be acquired using [user login](../../api_docs/open/login.md) : `POST /user/sign_in`

<!-- * [Show Accessible Entropy Sources](get.md) : `GET /entropy_sources/`
* [Create A Entropy Source](post.md) : `POST /entropy_sources/`
* [Show A Entropy Source](id/get.md) : `GET /entropy_sources/:id/`
* [Update A Entropy Source](id/put.md) : `PUT /entropy_sources/:id/`
* [Delete A Entropy Source](id/delete.md) : `DELETE /entropy_sources/:id/` -->
