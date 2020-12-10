# Accounts

- [Description](#description)
- [Properties](#properties)
- [Associations](#associations)
- [API endpoints](#api-endpoints)

## Description

`accounts` are collections of managed `wallet_addresses` belonging to the same blockchain network, grouped together for accounting purposes.

## Properties

| Properties | Description |
| --- | --- |
| `account_number` | An optional identifier that can be used as a cross reference for financial institutions  |
| `account_type` | Options include `bitcoin` and `ethereum`. Note there is currently no support for signing Ethereum transactions through the FreeRange webapp, but it is still useful for tracking.  |
| `address_type` | Used when the `account_type` is `bitcoin`. Options include `P2SH`, `P2SH-P2WSH`, `P2WSH` |
| `available_balance` | The available balance of the account. | 
| `border_color` | Used for the node's sprite border color. Rendered with ThreeJS/WebGl. |
| `background_color` | Used for the node's sprite border color. Rendered with ThreeJS/WebGl. |
| `description` | A short descrption of the `account`. |
| `email` | The email address to be used in case notifications regarding the `account` need to be sent.  |
| `name` | The name of the account. |
| `network` | The blockchain network of the `account_type`. Current options are `mainnet` and `testnet`, with future support planned for additional Ethereum testnets. |
| `required_signers` | The minimum number of signers needed for signing transactions. Can be one, but this will render the multi-sig bitcoin wallet feature non-functional for the FreeRange front end. Still useful for tracking non-compliance with C4 standards. |
| `token_balance` | *Only needed if tracking tokens.* This describes the balance of additional token types (such as ERC20) attributed to the wallet addresses of the account. Requires `token_contract_address`, `token_decimals`, and `token_symbol` |
| `token_contract_address` | *Only needed if tracking tokens.* This refers to the address of the actual token contract that manages the logic for the tokens. |
| `token_decimals` | *Only needed if tracking tokens.* The number of decimals specified in the token contract.  |
| `token_symbol` | *Only needed if tracking tokens.* The letter symbol used by the token. |
| `total_balance` | The total balance of the account. |
| `total_signers` | The total number of signers assigned to the account. |

## Associations

| Associations | Node | Relationship |
| --- | --- | --- |
| `has_one` | `organization` | `belongs_to` |
| `has_many` | `wallet_addresses` | `assigned_to` |
| `has_many` | `public_keys` | `assigned_to` |

## API endpoints

Endpoints for viewing and manipulating `accounts` that the `user` has permissions to access. Requires a valid token to be included in the header of the request. A token can be acquired using [user login](../../api_docs/open/login.md) : `POST /user/sign_in`

* [Show accessible accounts](get.md) : `GET /accounts/`
* [Create an account](post.md) : `POST /accounts/`
* [Show an account](id/get.md) : `GET /accounts/:id/`
* [Update an account](id/put.md) : `PUT /accounts/:id/`
* [Delete an account](id/delete.md) : `DELETE /accounts/:id/`