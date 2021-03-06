# Public keys

- [Description](#description)
- [Properties](#properties)
- [Associations](#associations)
- [API endpoints](#api-endpoints)

## Description

Cryptographic keys assigned to `accounts`, of which private key pairings are managed by `organizations`, and are used for signing `transactions`.

| Properties | Description |
| --- | --- |
| `method` | The method of generation for the public key. Used by Unchained Capital's Caravan Wallet adopted by FreeRange. Options include `TREZOR`, `LEDGER`, `HERMIT`, `XPUB`, and `TEXT` |
| `name` | The name of the public key. |
| `path` | The derivation path used by HD wallets to derive the public / private key pair. An example would be `m/45'/1'/0'`|
| `public_key` | The actual public key itself. An example would be `tpubDCqcyS5u4bec1UrHCEoDgUJziPtRU3f...` |

## Associations

| Associations | Node | Relationship |
| --- | --- | --- |
| `has_one` | `account` | `assigned_to` |
| `has_one` | `key_storage_device` | `private_key_pair_stored_on` |
| `has_one` | `wallet_address` | `required_for_signature` |

## API endpoints

Endpoints for viewing and manipulating `public_keys` that the `user` has permissions to access. Requires a valid token to be included in the header of the request. A token can be acquired using [user login](../../api_docs/open/login.md) : `POST /user/sign_in`

Coming soon...

<!-- * [Show Accessible Public Keys] : `GET /public_keys/`
* [Create A Public Key] : `POST /public_keys/`
* [Show A Public Key] : `GET /public_keys/:id/`
* [Update A Public Key] : `PUT /public_keys/:id/`
* [Delete A Public Key] : `DELETE /public_keys/:id/` -->
