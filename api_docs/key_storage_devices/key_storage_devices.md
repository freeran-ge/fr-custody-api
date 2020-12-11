# Key storage devices

- [Description](#description)
- [Properties](#properties)
- [Associations](#associations)
- [API endpoints](#api-endpoints)

## Description

A medium that stores public / private key pairs (ex. a deterministic HSM like a Trezor or an unencrypted piece of paper).

## Properties

| Properties | Description |
| --- | --- |
| `description` | A short description of the key storage device. |
| `name` | The name of the key storage device. |
| `share_build_with_community` | Posts a version of your `key_storage_device` to the community.  Options are `true` or `false` |
| `type` | The type of key storage device. ***Options still need to be defined*** |
| `risk_of_compromise` | Indicates the risk of a compromised key storage, on a scale from 1-99, with `1` indicating the lowest risk of compromise and and `99` offering the highest level of risk. An example of increased risk is poor access control standards or bad device sanitation procedures.|
| `url_link` | The url link where the item can be found. |

## Associations

| Associations | Node | Relationship |
| --- | --- | --- |
| `has_one` | `facility` | `stored_in` |
| `has_one` | `container` | `stored_in` |
| `has_many` | `key_managers` | `access` |
| `has_one` | `location` | `located_at` |
| `has_one` | `organization` | `belongs_to` |
| `has_many` | `public_keys` | `private_key_pair_stored_on` |
| `has_many` | `room` | `stored_in` |
| `has_one` | `seed` | `seeded` |

## API endpoints

Endpoints for viewing and manipulating `key_storage_devices` that the `user` has permissions to access. Requires a valid token to be included in the header of the request. A token can be acquired using [user login](../../api_docs/open/login.md) : `POST /user/sign_in`

Coming soon...
<!-- * [Show Accessible Key Storage Devices](api_docs/key_storage_devices/get.md) : `GET /key_managers/`
* [Create A Key Storage Device](api_docs/key_storage_devices/post.md) : `POST /key_storage_devices/`
* [Show A Key Storage Device](api_docs/key_storage_devices/id/get.md) : `GET /key_storage_devices/:id/`
* [Update A Key Storage Device](api_docs/key_storage_devices/id/put.md) : `PUT /key_storage_devices/:id/`
* [Delete A Key Storage Device](api_docs/key_storage_devices/id/delete.md) : `DELETE /key_storage_devices/:id/` -->
