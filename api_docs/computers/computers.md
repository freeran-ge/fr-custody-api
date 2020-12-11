# Computers

- [Description](#description)
- [Properties](#properties)
- [Associations](#associations)
- [API endpoints](#api-endpoints)

## Description

Electronic devices used in processing and / or storing data related to key management, including `key_ceremonies`. An example would be an "air-gapped" notebook.

## Properties

| Properties | Description |
| --- | --- |
| `description` | A short description of the computer. |
| `is_bluetooth_physically_connected` | Boolean. Options are `true` or `false` |
| `is_gsm_physically_connected` | Boolean. Options are `true` or `false` |
| `is_necessary_software_installed` | Boolean. Options are `true` or `false` |
| `is_wifi_physically_connected` | Boolean. Options are `true` or `false` |
| `is_writeable_storage_present` | Boolean. Options are `true` or `false` |
| `name` | The name of the computer. |
| `risk_of_compromise` | Indicates the risk of a compromised computer in use by the organization, on a scale from 1-99, with `1` indicating the lowest risk of compromise and and `99` offering the highest level of risk. An example of increased risk is using a seed mnenomic generator that is connected to the internet.|
| `share_build_with_community` | Posts a version of your computer build to the community.  Options are `true` or `false` |
| `type` | The type of computer. Options include `desktop`, `laptop`, `notebook`, `single_board_computer`, or `other` |
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

Endpoints for viewing and manipulating `computers` that the `user` has permissions to access. Requires a valid token to be included in the header of the request. A token can be acquired using [user login](../../api_docs/open/login.md) : `POST /user/sign_in`

<!-- * [Show accessible computers](get.md) : `GET /computers/`
* [Create a computer](post.md) : `POST /computers/`
* [Show a computer](id/get.md) : `GET /computers/:id/`
* [Update a computer](id/put.md) : `PUT /computers/:id/`
* [Delete a computer](id/delete.md) : `DELETE /computers/:id/` -->
