# Show Graph Data Relationships from a Single Organization

> *Note: this section is a work in progress*

Shows graph data relationships from a single Organzation if current User has access permissions to it.

**URL** : `/organizations/:id/graph_data`

**URL Parameters** : `id=[string]` where `id` is the ID of the Organization on the
server.

**Method** : `GET`

**Auth required** : YES

**Permissions required** :

**Data**: `{}`

## Success Response

**Condition** : If Organization exists and Authorized User has required permissions.

**Code** : `200 OK`

**Content example**

```json
{
    "organizations": [
        {
            "keys": [
                "{nodes: nl, links: rl}"
            ],
            "values": [
                {
                    "nodes": [
                        {
                            "entity_type": "Wyoming LLC",
                            "address": null,
                            "background_color": "#008000",
                            "risk_score": 14,
                            "name": "Runolfsson Group",
                            "id": 27,
                            "border_color": "#008000",
                            "uuid": "3abe4145-7303-44c2-8831-c46d1c368e41",
                            "labels": [
                                "Organization"
                            ]
                        },
                        {
                            "entity_type": null,
                            "address": null,
                            "background_color": "#0747A6",
                            "risk_score": null,
                            "name": "Motion Pictures and Film",
                            "id": 34,
                            "border_color": "#008000",
                            "uuid": "eb7083fe-b7a0-43c9-83a1-a71fa8326e7f",
                            "labels": [
                                "Account"
                            ]
                        },
                        {
                            "entity_type": null,
                            "address": "2NF9W5ZD4HUtZiBmySNLttH5EWGyfCD85hm",
                            "background_color": null,
                            "risk_score": null,
                            "name": "Motion Pictures and Film Wallet Address 1 of 1",
                            "id": 35,
                            "border_color": null,
                            "uuid": "9ffefcd1-105f-4f2e-a04d-928f2d5bf3f1",
                            "labels": [
                                "WalletAddress"
                            ]
                        },
                        {
                            "entity_type": null,
                            "address": null,
                            "background_color": null,
                            "risk_score": null,
                            "name": "Motion Pictures and Film Key 1 of 3",
                            "id": 36,
                            "border_color": null,
                            "uuid": "210f96b7-c438-4dcb-8e5e-92c9b82a7277",
                            "labels": [
                                "PublicKey"
                            ]
                        },
                        {
                            "entity_type": null,
                            "address": null,
                            "background_color": "#0747A6",
                            "risk_score": null,
                            "name": "Trezor Model T",
                            "id": 31,
                            "border_color": "#008000",
                            "uuid": "822f9705-b23f-4919-93c9-4f089beee225",
                            "labels": [
                                "KeyStorageDevice"
                            ]
                        },
                        {
                            "entity_type": null,
                            "address": null,
                            "background_color": null,
                            "risk_score": null,
                            "name": "Motion Pictures and Film Key 2 of 3",
                            "id": 37,
                            "border_color": null,
                            "uuid": "49a4d712-5acf-4a14-897b-68c273ac070e",
                            "labels": [
                                "PublicKey"
                            ]
                        },
                        {
                            "entity_type": null,
                            "address": null,
                            "background_color": "#0747A6",
                            "risk_score": null,
                            "name": "Trezor Model T",
                            "id": 32,
                            "border_color": "#008000",
                            "uuid": "e03f51a5-c163-470a-9fef-456f13a390e5",
                            "labels": [
                                "KeyStorageDevice"
                            ]
                        },
                        {
                            "entity_type": null,
                            "address": null,
                            "background_color": null,
                            "risk_score": null,
                            "name": "Motion Pictures and Film Key 3 of 3",
                            "id": 38,
                            "border_color": null,
                            "uuid": "7d6d3754-b694-4df7-a42a-b8dca4a441cc",
                            "labels": [
                                "PublicKey"
                            ]
                        },
                        {
                            "entity_type": null,
                            "address": null,
                            "background_color": "#0747A6",
                            "risk_score": null,
                            "name": "Trezor Model T",
                            "id": 33,
                            "border_color": "#008000",
                            "uuid": "f6dc6c7b-6093-43b0-a37a-c756d74d509d",
                            "labels": [
                                "KeyStorageDevice"
                            ]
                        },
                        {
                            "entity_type": null,
                            "address": null,
                            "background_color": null,
                            "risk_score": null,
                            "name": "Sunshine Schmeler",
                            "id": 28,
                            "border_color": null,
                            "uuid": "e57a1140-a659-412b-b01b-46b0ac801ca0",
                            "labels": [
                                "KeyManager"
                            ]
                        },
                        {
                            "entity_type": null,
                            "address": null,
                            "background_color": null,
                            "risk_score": null,
                            "name": "Miss Corrina Macejkovic",
                            "id": 29,
                            "border_color": null,
                            "uuid": "f13f303c-6ac7-4cf8-bb0c-4696b104b315",
                            "labels": [
                                "KeyManager"
                            ]
                        },
                        {
                            "entity_type": null,
                            "address": null,
                            "background_color": null,
                            "risk_score": null,
                            "name": "Oswaldo Kautzer",
                            "id": 30,
                            "border_color": null,
                            "uuid": "21fbf91f-369c-4e58-b0e6-24fa8316be64",
                            "labels": [
                                "KeyManager"
                            ]
                        }
                    ],
                    "links": [
                        {
                            "color": "#008000",
                            "source": 27,
                            "type": "BENEFICIARY_OF",
                            "value": null,
                            "target": 34
                        },
                        {
                            "color": "#0747A6",
                            "source": 34,
                            "type": "GENERATED",
                            "value": null,
                            "target": 35
                        },
                        {
                            "color": "#0747A6",
                            "source": 36,
                            "type": "ASSIGNED_TO",
                            "value": null,
                            "target": 34
                        },
                        {
                            "color": "#008000",
                            "source": 36,
                            "type": "PRIVATE_KEY_PAIR_STORED_ON",
                            "value": null,
                            "target": 31
                        },
                        {
                            "color": "#0747A6",
                            "source": 37,
                            "type": "ASSIGNED_TO",
                            "value": null,
                            "target": 34
                        },
                        {
                            "color": "#008000",
                            "source": 37,
                            "type": "PRIVATE_KEY_PAIR_STORED_ON",
                            "value": null,
                            "target": 32
                        },
                        {
                            "color": "#0747A6",
                            "source": 38,
                            "type": "ASSIGNED_TO",
                            "value": null,
                            "target": 34
                        },
                        {
                            "color": "#008000",
                            "source": 38,
                            "type": "PRIVATE_KEY_PAIR_STORED_ON",
                            "value": null,
                            "target": 33
                        },
                        {
                            "color": "#008000",
                            "source": 28,
                            "type": "SERVES",
                            "value": null,
                            "target": 27
                        },
                        {
                            "color": "#008000",
                            "source": 28,
                            "type": "HAS_CUSTODY_OF",
                            "value": null,
                            "target": 31
                        },
                        {
                            "color": "#008000",
                            "source": 29,
                            "type": "SERVES",
                            "value": null,
                            "target": 27
                        },
                        {
                            "color": "#008000",
                            "source": 29,
                            "type": "HAS_CUSTODY_OF",
                            "value": null,
                            "target": 32
                        },
                        {
                            "color": "#008000",
                            "source": 30,
                            "type": "SERVES",
                            "value": null,
                            "target": 27
                        },
                        {
                            "color": "#008000",
                            "source": 30,
                            "type": "HAS_CUSTODY_OF",
                            "value": null,
                            "target": 33
                        }
                    ]
                }
            ],
            "wrap": true
        }
    ]
}
```

## Error Responses

**Condition** : If Organization does not exist with `id` of provided `id` parameter.

**Code** : `404 NOT FOUND`

**Content** : `{}`


### Or

**Condition** : If Organization exists but Authorized User does not have required
permissions.

**Code** : `401 UNAUTHORIZED`

**Content** :

```json
{"error": "Unauthorized"}
```

## Notes

There are security issues:

* This view allows existing users to test for existence of Organizations that exist
    but that they do not have access to.
* In the development enviroment, the 404 content is very verbose. Must check to see  if this is true in production.
