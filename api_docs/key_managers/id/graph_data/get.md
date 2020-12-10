# Show Graph Data Relationships for a Single Key Manager

Shows graph data relationships of a Key Manager if current User has access permissions to it.

**URL** : `/key_managers/:id/graph_data`

**URL Parameters** : `id=[string]` where `id` is the ID of the Key Manager on the
server.

**Method** : `GET`

**Auth required** : YES

**Permissions required** :

**Data**: `{}`

## Success Response

**Condition** : If the Key Manager exists and the Authorized User has required permissions.

**Code** : `200 OK`

**Content example**

```json
{
    "key_managers": [
        {
            "keys": [
                "{nodes: nl, links: rl}"
            ],
            "values": [
                {
                    "nodes": [
                        {
                            "entity_type": null,
                            "address": null,
                            "background_color": null,
                            "risk_score": null,
                            "name": "Mervin Reilly V",
                            "id": 7,
                            "border_color": null,
                            "uuid": "2d995619-c76a-460f-b4c3-5ec546cfef44",
                            "labels": [
                                "KeyManager"
                            ]
                        },
                        {
                            "entity_type": "Wyoming LLC",
                            "address": null,
                            "background_color": "#008000",
                            "risk_score": 14,
                            "name": "Kassulke-Funks",
                            "id": 4,
                            "border_color": "#008000",
                            "uuid": "a6d1a3ce-ab51-42d0-b824-90022777c4ad",
                            "labels": [
                                "Organization"
                            ]
                        },
                        {
                            "entity_type": null,
                            "address": null,
                            "background_color": "#0747A6",
                            "risk_score": null,
                            "name": "Trezor Model T",
                            "id": 10,
                            "border_color": "#008000",
                            "uuid": "fb04b6c3-04c8-4726-976c-49f50dada0fb",
                            "labels": [
                                "KeyStorageDevice"
                            ]
                        }
                    ],
                    "links": [
                        {
                            "color": "#008000",
                            "source": 7,
                            "type": "SERVES",
                            "value": null,
                            "target": 4
                        },
                        {
                            "color": "#008000",
                            "source": 7,
                            "type": "HAS_CUSTODY_OF",
                            "value": null,
                            "target": 10
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

**Condition** : If Key Manager does not exist with `id` of provided `id` parameter.

**Code** : `404 NOT FOUND`

**Content** : `{}`


### Or

**Condition** : If the Key Manager exists but the Authorized User does not have required
permissions.

**Code** : `401 UNAUTHORIZED`

**Content** :

```json
{"error": "Unauthorized"}
```

## Notes

There are security issues:

* This view allows existing users to test for existence of Key Managers that exist
    but that they do not have access to.
* In the development enviroment, the 404 content is very verbose. Must check to see  if this is true in production.
