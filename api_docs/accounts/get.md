# Show accessible accounts

Show all `accounts` the active `user` can access.

**URL** : `/accounts/`

**Method** : `GET`

**Auth required** : Yes

**Permissions Required** : None

**Data constraints**

```json
{}
```

## Success response

**Code** : `200 OK`

**Response Body Example**

```json
{
  "accounts": [
    {
      "account": {
        "created_at": "2020-12-02T15:35:03.000+00:00",
        "updated_at": "2020-12-02T15:35:03.000+00:00",
        "account_number": "4625884251",
        "account_type": "bitcoin",
        "address_type": "P2SH",
        "available_balance": "0.60012498",
        "border_color": "#008000",
        "background_color": "#0747A6",
        "description": "Function-based user-facing knowledge base",
        "email": "diane_gutkowski@mayert-kessler.biz",
        "name": "Fishery",
        "network": "testnet",
        "required_signers": 2,
        "risk_score": null,
        "total_balance": "0.60012498",
        "total_signers": 3,
        "user_id": "5cbcfcfd-0226-48e9-999e-3f7bd7a60d80",
        "public_keys": [
          {
            "created_at": "2020-12-02T15:35:04.000+00:00",
            "updated_at": "2020-12-02T15:35:04.000+00:00",
            "name": "Fishery Key 3 of 3",
            "path": "m/45'/1'/2'",
            "public_key": "tpubDCqcyS5kiw7dsRDayULW6tMkc86N5o9WoGnV7LdKdhyQu6khWp1X3NRS3EnycKTE2d88aSkqYcvJg2MvV8wxVCZCtKT7VAEDxKhD1BGk5ez",
            "method": "trezor",
            "user_id": "5cbcfcfd-0226-48e9-999e-3f7bd7a60d80",
            "id": "f01ec423-5873-44b5-a059-a100d7dffb28"
          },
          {
            "created_at": "2020-12-02T15:35:04.000+00:00",
            "updated_at": "2020-12-02T15:35:04.000+00:00",
            "name": "Fishery Key 2 of 3",
            "path": "m/45'/1'/1'",
            "public_key": "tpubDCqcyS5kiw7dsRDayULW6tMkc86N5o9WoGnV7LdKdhyQu6khWp1X3NRS3EnycKTE2d44aSkqYcvJg2MvV8wxVCZCtKT7VAEDxKhD1BGk5eq",
            "method": "trezor",
            "user_id": "5cbcfcfd-0226-48e9-999e-3f7bd7a60d80",
            "id": "045cab17-abb1-4f82-81fb-1c64091588ae"
          },
          {
            "created_at": "2020-12-02T15:35:04.000+00:00",
            "updated_at": "2020-12-02T15:35:04.000+00:00",
            "name": "Fishery Key 1 of 3",
            "path": "m/45'/1'/0'",
            "public_key": "tpubDCqcyS5u4bec1UrHCEoDgUJziPtRU3f7MzWyUgxHzZkt8zvMCv25ap3KFs2c9iy2CwFQHaeFzQwtFTirrYbmVWdBL2uc6BDrn7iMnZGMx3X",
            "method": "trezor",
            "user_id": "5cbcfcfd-0226-48e9-999e-3f7bd7a60d80",
            "id": "ab64a1d0-3d99-45e2-8c17-369cda491b46"
          }
        ],
        "id": "2a067c63-05a3-47ee-9f34-b0cd8ab9ba85"
      }
    }
  ]
}
```
