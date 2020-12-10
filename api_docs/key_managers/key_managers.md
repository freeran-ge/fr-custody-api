# Key managers

- [Description](#description)
- [Properties](#properties)
- [Associations](#associations)
- [API endpoints](#api-endpoints)

## Description

Members of `organizations` that have access to `key_storage_devices`, `seed_backups` and / or help generate `seeds` during `key_ceremonies

| Properties | Description |
| --- | --- |
| `description` | A short description of the key manager. |
| `email` | The key manager's email address. Can be used for login as a future feature |
| `employee_id` | Useful as a cross-reference feature if an organization has an existing HR infrastructure |
| `has_background_check` | A booleen value to check if the Key Manager was properly background checked. |
| `name` | If the key manager has a name, this is a good place to document it. |
| `phone_number` | Contact phone number. |
| `risk_of_fraud_collusion` | Indicates the risk of fraud collusion with another `key_manager` on a scale from 1-99, with `1` indicating the lowest risk of fraud collusion and and `99` offering the highest level of risk. |
| `title` | The formal title of the key manager. |

| Associations | Node | Relationship |
| --- | --- | --- |
| `has_many` | `facilities` | `access` |
| `has_many` | `containers` | `access` |
| `has_many` | `key_ceremonies` | `participated_in` |
| `has_many` | `key_storage_devices` | `access` |
| `has_many` | `entropy_sources` | `access` |
| `has_many` | `locations` | `access` |
| `has_one` | `location` | `located_at` |
| `has_many` | `rooms` | `access` |
| `has_one` | `organization` | `belongs_to` |

## API endpoints

Endpoints for viewing and manipulating the Key Managers that the Authenticated User
has permissions to access.

* [Show Accessible Key Managers](api_docs/key_managers/get.md) : `GET /key_managers/`
* [Create A Key Manager](api_docs/key_managers/post.md) : `POST /key_managers/`
* [Show A Key Manager](api_docs/key_managers/id/get.md) : `GET /key_managers/:id/`
* [Show A Key Manager's Relationships](api_docs/key_managers/id/graph_data/get.md) : `GET /key_managers/:id/graph_data`
* [Update A Key Manager](api_docs/key_managers/id/put.md) : `PUT /key_managers/:id/`
* [Delete A Key Manager](api_docs/key_managers/id/delete.md) : `DELETE /key_managers/:id/`