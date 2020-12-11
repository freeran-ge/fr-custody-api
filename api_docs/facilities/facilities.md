# Facilities

- [Description](#description)
- [Properties](#properties)
- [Associations](#associations)
- [API endpoints](#api-endpoints)

## Description

An installation, building, or segerated space within used for the operations of organizations. Examples would be a house, bank branch, etc. Some facilities will be more hardened and have different levels of access control than others.

| Properties | Description |
| --- | --- |
| `description` | A short description of the facility. |
| `has_access_records_stored_off_site` | Options are `true` or `false` |
| `has_alarms` | Options are `true` or `false` |
| `has_audio_recording` | Options are `true` or `false` |
| `has_security_cameras` | Options are `true` or `false` |
| `has_windows` | Options are `true` or `false` |
| `is_monitored_by_security` | Options are `true` or `false` |
| `is_a_stand_alone_building` | Options are `true` or `false` |
| `material_of_ceiling` | Description |
| `material_of_walls` | Description |
| `material_of_floor` | Description |
| `material_of_doors` | Description |
| `name` | The name of the facility. |
| `resistance_to_blast` | Indicates the resistance to blast damage on a scale from 1-99, with `1` offering no protective resistance to blast damage, and `99` offering the highest level of resistance to blast damage. |
| `resistance_to_earthquakes` | Indicates the resistance to earthquake damage on a scale from 1-99, with `1` offering no protective resistance to earthquake damage, and `99` offering the highest level of resistance to earthquake damage. |
| `resistance_to_emp` | Indicates the resistance to electromagnetic pulse (EMP) damage on a scale from 1-99, with `1` offering no protective resistance to EMP damage, and `99` offering the highest level of resistance to EMP damage. |
| `resistance_to_fire` | Indicates the resistance to fire damage on a scale from 1-99, with `1` offering no protective resistance to fire damage, and `99` offering the highest level of resistance to fire damage. |
| `resistance_to_flood` | Indicates the resistance to flood damage on a scale from 1-99, with `1` offering no protective resistance to damage, and `99` offering the highest level of resistance to flood damage. |
| `resistance_to_forceable_attack` | Indicates the resistance to penetrative forceable attack on a scale from 1-99, with `1` offering no protective resistance to penetrative forceable attack, and `99` offering the highest level of resistance to penetrative forceable attack. |
| `resistance_to_heat` | Indicates the resistance to heat damage on a scale from 1-99, with `1` offering no protective resistance to heat damage, and `99` offering the highest level of resistance to heat damage. |
| `resistance_to_hurricanes` | Indicates the resistance to hurricane damage on a scale from 1-99, with `1` offering no protective resistance to hurricane damage, and `99` offering the highest level of resistance to hurricane damage. |
| `resistance_to_tornadoes` | Indicates the resistance to tornado damage on a scale from 1-99, with `1` offering no protective resistance to tornado damage, and `99` offering the highest level of resistance to tornado damage. |
| `security_cameras_are_hardened` | Options are `true` or `false` |
| `share_build_with_community` | Posts a version of your facility build to the community.  Options are `true` or `false` |
| `type` | The type of facility. |
| `uses_biometric_access_control` | Options are `true` or `false` |
| `uses_login_credentials_access_control` | Options are `true` or `false` |
| `uses_tangible_device_access_control` | Options are `true` or `false` |

## Associations

| Associations | Node | Relationship |
| --- | --- | --- |
| `has_many` | `containers` | `stored_in` |
| `has_many` | `key_ceremonies` | `used_in` |
| `has_many` | `key_managers` | `access` |
| `has_many` | `key_storage_devices` | `stored_in` |
| `has_many` | `seed_backups` | `stored_in` |
| `has_many` | `entropy_sources` | `stored_in` |
| `has_one` | `location` | `located_at` |
| `has_many` | `rooms` | `stored_in` |

## API endpoints

Endpoints for viewing and manipulating `facilities` that the `user` has permissions to access. Requires a valid token to be included in the header of the request. A token can be acquired using [user login](../../api_docs/open/login.md) : `POST /user/sign_in`
