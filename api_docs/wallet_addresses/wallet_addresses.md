# Wallet addresses

- [Description](#description)
- [Properties](#properties)
- [Associations](#associations)
- [API endpoints](#api-endpoints)

## Description

An address on a blockchain network used for the assignment and accounting of digital assets.

| Properties | Description |
| --- | --- |
| `account_type` | Options include `bitcoin` and `ethereum`. Note there is currently no support for signing Ethereum transactions through the FreeRange webapp, but it is still useful for tracking.  |
| `address_type` | Used when the `account_type` is `bitcoin`. Options include `P2SH`, `P2SH-P2WSH`, `P2WSH` |
| `available_balance` | The available balance of the `wallet_address`. | 
| `address` | The actual address of the wallet. |
| `name` | The name of the wallet address. |
| `network` | The blockchain network of the `wallet_address`. Current options are `mainnet` and `testnet`, with future support planned for additional Ethereum testnets. |
| `token_balance` | *Only needed if tracking tokens.* This describes the balance of additional token types (such as ERC20) attributed to the `wallet address`. Requires `token_contract_address`, `token_decimals`, and `token_symbol` |
| `token_contract_address` | *Only needed if tracking tokens.* This refers to the address of the actual token contract that manages the logic for the tokens. |
| `token_decimals` | *Only needed if tracking tokens.* The number of decimals specified in the token contract.  |
| `token_symbol` | *Only needed if tracking tokens.* The letter symbol used by the token. |
| `total_balance` | The total balance of the `wallet_address`. |

| Associations | Node | Relationship |
| --- | --- | --- |
| `has_one` | `account` | `assigned_to` |
| `has_many` | `public_keys` | `required_for_signature` |

## API endpoints

Endpoints for viewing and manipulating the `wallet_addresses` that the `user`
has permissions to access.

* [Show Accessible Wallet Addresses] : `GET /wallet_addresses/`
* [Create A Wallet Address] : `POST /wallet_addresses/`
* [Show A Wallet Address] : `GET /wallet_addresses/:id/`
* [Update A Wallet Address] : `PUT /wallet_addresses/:id/`
* [Delete A Wallet Address] : `DELETE /wallet_addresses/:id/`