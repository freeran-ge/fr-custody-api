# Show Single Organization

Show a single Organzation if current User has access permissions to it.

**URL** : `/organizations/:id/`

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
    "organizations": {
        "organization": {
            "created_at": "2020-11-25T19:21:39.000+00:00",
            "updated_at": "2020-11-25T19:21:39.000+00:00",
            "border_color": "#008000",
            "background_color": "#008000",
            "contact_name": null,
            "contact_title": null,
            "contact_phone": null,
            "email": "amber@fr.financial",
            "entity_type": "company",
            "name": "Runolfsson Group",
            "user_id": "6491857b-ef71-487c-ba77-403ac802a32f",
            "accounts": [
                {
                    "created_at": "2020-11-25T19:21:39.000+00:00",
                    "updated_at": "2020-11-25T19:21:39.000+00:00",
                    "account_number": "8138021099",
                    "address_type": "P2SH",
                    "available_balance": "0.60012498",
                    "border_color": "#008000",
                    "background_color": "#0747A6",
                    "description": "Re-contextualized bottom-line circuit",
                    "email": "adelle@douglas-kreiger.com",
                    "name": "Motion Pictures and Film",
                    "network": "testnet",
                    "organization_id": null,
                    "required_signers": 2,
                    "risk_score": null,
                    "total_signers": 3,
                    "total_balance": "0.60012498",
                    "id": "eb7083fe-b7a0-43c9-83a1-a71fa8326e7f"
                }
            ],
            "key_managers": [
                {
                    "created_at": "2020-11-25T19:21:39.000+00:00",
                    "updated_at": "2020-11-25T19:21:39.000+00:00",
                    "description": "Programmable systemic architecture",
                    "email": "moises_kemmer@morar-quitzon.co",
                    "employee_id": "GB84WKZK02225577128478",
                    "title": "Direct Coordinator",
                    "name": "Oswaldo Kautzer",
                    "organization_id": "3abe4145-7303-44c2-8831-c46d1c368e41",
                    "phone_number": "(223) 102-3365",
                    "id": "21fbf91f-369c-4e58-b0e6-24fa8316be64"
                },
                {
                    "created_at": "2020-11-25T19:21:39.000+00:00",
                    "updated_at": "2020-11-25T19:21:39.000+00:00",
                    "description": "Programmable bandwidth-monitored adapter",
                    "email": "jamey_haley@nikolaus.biz",
                    "employee_id": "GB16IWIS48364455366435",
                    "title": "Sales Facilitator",
                    "name": "Miss Corrina Macejkovic",
                    "organization_id": "3abe4145-7303-44c2-8831-c46d1c368e41",
                    "phone_number": "909.770.1008",
                    "id": "f13f303c-6ac7-4cf8-bb0c-4696b104b315"
                },
                {
                    "created_at": "2020-11-25T19:21:39.000+00:00",
                    "updated_at": "2020-11-25T19:21:39.000+00:00",
                    "description": "Decentralized optimizing framework",
                    "email": "julian@kautzer.info",
                    "employee_id": "GB52ZXPV45188518136855",
                    "title": "Technology Architect",
                    "name": "Sunshine Schmeler",
                    "organization_id": "3abe4145-7303-44c2-8831-c46d1c368e41",
                    "phone_number": "711.844.4270",
                    "id": "e57a1140-a659-412b-b01b-46b0ac801ca0"
                }
            ],
            "id": "3abe4145-7303-44c2-8831-c46d1c368e41"
        }
    }
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
