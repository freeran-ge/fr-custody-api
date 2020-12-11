# Seed Backups

- [Description](#description)
- [Properties](#properties)
- [Associations](#associations)
- [API endpoints](#api-endpoints)

## Description

(M of N) physical mediums (ex. engraved metal plates) used to distribute portions of a `seed` amongst different geographical locations, allowing `organizations` to recover access to digital assets in case of `key_storage_device` failure. Idealy resistant to EMP, blast, fire, flood, etc

| Properties | Description |
| --- | --- |
| `description` | A short description of the seed backup. |
| `is_encrypted` | Boolean on whether the seed backup is encrypted. Options are `true` or `false` |
| `minimum_shares` | The minimum number of shares needed to reproduce the seed |
| `name` | The name of the seed backup. An example would be 'Seed backup 1 of 3' |
| `notes` | Additional notes that might be useful. |
| `risk_of_compromise` | Indicates the risk of a compromised seed backup, on a scale from 1-99, with `1` indicating the lowest risk of compromise and and `99` offering the highest level of risk. An example of increased risk is using an unencrypted paper storage medium.|
| `storage_medium` | The storage medium of seed backup. Options include `electronic`, `metal`, `paper`, or `other` |
| `total_shares` | The total number of shares created |
| `type` | The type of seed backup scheme. Options include `split_mnemonic`, `shamir`, `whole`, or `other` |

# Associations

| Associations | Node | Relationship |
| --- | --- | --- |
| `has_one` | `facility` | `stored_in` |
| `has_one` | `container` | `stored_in` |
| `has_many` | `key_managers` | `has_access_to` |
| `has_one` | `location` | `located_at` |
| `has_one` | `room` | `stored_in` |
| `has_one` | `seed` | `generated` |

## API endpoints

Endpoints for viewing and manipulating `seed_backups` that the `user` has permissions to access. Requires a valid token to be included in the header of the request. A token can be acquired using [user login](../../api_docs/open/login.md) : `POST /user/sign_in`

Coming soon...

<!-- * [Show Accessible Seed Backups](api_docs/seed_backups/get.md) : `GET /seed_backups/`
* [Create A Seed Backup](api_docs/seed_backups/post.md) : `POST /seed_backups/`
* [Show A Seed Backup](api_docs/seed_backups/id/get.md) : `GET /seed_backups/:id/`
* [Update A Seed Backup](api_docs/seed_backups/id/put.md) : `PUT /seed_backups/:id/`
* [Delete A Seed Backup](api_docs/seed_backups/id/delete.md) : `DELETE /seed_backups/:id/` -->
