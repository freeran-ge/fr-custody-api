# Create an account

Creates an `account` for the `user`. Each `user` can have many `accounts` which are managed by the `organization` it is assigned to.

**URL** : `/accounts/`

**Method** : `POST`

**Auth required** : YES

**Permissions required** : None

**Data constraints**

Partial data is allowed, but `account_type`, `address_type`, `network`, `required_signers`, and `total_signers` must be provided to be created.
Current support is for `bitcoin` only. Future support planned for Ethereum 2.0 native multi-sig (does not require a smart contract).

```json
{
  "account": {
    "account_number": "[string]",
    "account_type": "must be ['Bitcoin']",
    "address_type": "must be ['P2SH', 'P2SH-P2WSH', or 'P2WSH']",
    "description": "[string]",
    "email": "[must be a valid email address format]",
    "name": "[string]",
    "network": "[must be 'mainnet' or 'testnet]",
    "required_signers": "[must choose an integer between 2 to 7]",
    "total_signers": "[must choose an integer between 2 to 7]"
  }
}
```

**Data example** Fields below show the minimal data fields required.

```json
{
  "account": {
    "account_type": "bitcoin",
    "address_type": "P2SH",
    "network": "testnet",
    "required_signers": 2,
    "total_signers": 7
  }
}
```

## Success Response

**Condition** : If everything is OK.

**Code** : `200 OK`

**Content example**

```json
{
  "account": {
    "created_at": "2020-11-27T20:40:57.000+00:00",
    "updated_at": "2020-11-27T20:40:57.000+00:00",
    "account_number": "3298818984",
    "address_type": "P2SH",
    "available_balance": "0.60012498",
    "border_color": "#008000",
    "background_color": "#0747A6",
    "description": "Visionary high-level ability",
    "email": "mercedez.casper@effertz.org",
    "name": "Market Research",
    "network": "testnet",
    "required_signers": 2,
    "risk_score": null,
    "total_signers": 3,
    "total_balance": "0.60012498"
  }
}
```

## Error Responses

<!-- **Condition** : If Organization already exists for User.

**Code** : `303 SEE OTHER`

**Headers** : `Location: http://testserver/api/Organizations/123/`

**Content** : `{}`

### Or -->

**Condition** : If name field is missing.

**Code** : `400 BAD REQUEST`

**Content example**

```json
{
  "error": "BAD REQUEST"
}
```
