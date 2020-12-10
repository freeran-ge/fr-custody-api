# Update Account

Updates the Account if the Authenticated User has permission.

**URL** : `/accounts/:id/`

**Method** : `PUT`

**Auth required** : YES

**Permissions required** : YES

**Data constraints**

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
                "total_signers": "[must choose an integer between 2 to 7]",
    }
}
```

**Data example** Partial data is allowed.

```json
{
   "account": {
                
                "account_type": "bitcoin",
                "address_type": "P2SH",
                "network": "testnet",
                "required_signers": 2,
                "total_signers": 7,
    }
}
```

## Success Responses

**Condition** : Update can be performed either fully or partially by Authorized User.

**Code** : `200 OK`

**Content example** : For the example above, when the 'name' is updated and
posted to `/accounts/5b37d3b8-4438-4dde-a634-83a740a39388/`...

```json

{
    "accounts": {
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
                "total_balance": "0.60012498",
            }
    }
} 

```

## Error Response

**Condition** : Account does not exist

**Code** : `404 NOT FOUND`

**Content** : `{}`

### Or

**Condition** : Authenticated User does not have permission.

**Code** : `401 Unauthorized`

**Content** : `"error": "UNAUTHORIZED"`

## Notes

### Data ignored

Endpoint will ignore irrelevant and read-only data such as parameters that
don't exist, or `id` fields which are not editable.

E.g. if Account already exits:

**Data example**

```json
{
    "wibble": "flobble",
    "id": 987,
    "name" : "Giggles"
}
```

**Code** : `200 OK`

**Content example**

```json
{
    "id": 123,
    "name": "Giggles",
}
```