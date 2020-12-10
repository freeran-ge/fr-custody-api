# Key Ceremonies

- [Description](#description)
- [Properties](#properties)
- [Associations](#associations)
- [API endpoints](#api-endpoints)

## Description

Procedural events where `organizations` generates unique public / private root keys used to store digital assets

| Properties | Description |
| --- | --- |
| `date` | The date of the key ceremony in `YYYY-MM-DD` format |
| `description` | A short description of the key_ceremony. |
| `name` | The name of the key ceremony. |
| `notes` | Any additional notes pertaining to the ceremony. |
| `risk_of_compromise` | Indicates the risk of a compromised key generation ceremony, on a scale from 1-99, with `1` indicating the lowest risk of compromise and and `99` offering the highest level of risk. An example of increased risk is using a seed mnenomic generator that is connected to the internet.|

| Associations | Node | Relationship |
| --- | --- | --- |
| `has_many` | `entropy_sources` | `used_in` |
| `has_many` | `key_managers` | `participated_in` |
| `has_one` | `location` | `located_at` |
| `has_one` | `room` | `used_in` |
| `has_many` | `seeds` | `generated` |
| `has_many` | `seed_backups` | `generated` |
