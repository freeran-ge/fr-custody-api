# FreeRange Custody API

## Table of Contents
- [Introduction](#introduction)
  - [Key features](#key-features)
- [Database schema overview](#database-schema-overview)
  - [Nodes](#nodes)
    - [General](#general)
    - [Key management related](#key-management-related)
    - [Other](#other)
  - [Relationships](#relationships)
    - [General](#general-1)
    - [Key management related](#key-management-related-1)
- [Node details with API endpoints](#node-details-with-api-endpoints)
  - [`accounts`](api_docs/accounts/accounts.md)
  - [`computers`](api_docs/computers/computers.md)
  - [`containers`](api_docs/containers/containers.md)
  - [`entropy_sources`](api_docs/entropy_sources/entropy_sources.md)
  - [`facilities`](api_docs/facilities/facilities.md)
  - [`key_ceremonies`](api_docs/key_ceremonies/key_ceremonies.md)
  - [`key_managers`](api_docs/key_managers/key_managers.md)
  - [`key_storage_devices`](api_docs/key_storage_devices/key_storage_devices.md)
  - [`locations`](api_docs/locations/locations.md)
  - [`organizations`](api_docs/organizations/organizations.md)
  - [`public_keys`](api_docs/public_keys/public_keys.md)
  - [`rooms`](api_docs/rooms/rooms.md)
  - [`seeds`](api_docs/seeds/seeds.md)
  - [`seed_backups`](api_docs/seed_backups/seed_backups.md)
  - [`wallet_addresses`](api_docs/wallet_addresses/wallet_addresses.md)

## Introduction

`fr-custody-api` is a backend solution for **designing**, **managing**, and / or **auditing** an organization's crypto self-custody operations. 

> *Note: Originally designed for banks seeking to comply with the Wyoming Division of Banking's rules for digital asset custody.* 

Useful for: 
- Financial institutions
- Bank examiners
- Auditing firms
- Private offices
- Any group or organization wanting to self-custody crypto-assets.

### Key features

**Design bank-grade self-custody solutions**
- Document and plan out the infrastructure needed for self-custody operations. 
- Analyze an organization's existing facilities, or plan out a system that leverages the safe deposit boxes of other banks. 
- Model how many team members are needed to act as key managers.
- and more...

**Manage self-custody operations at scale** 
- Track team member access to key storage devices and seed backups.
- Generate and manage accounts.
- Document everything needed for key ceremony events.   
- and more... 
 
**Powerful analytics tools for auditing and risk management.** 
- Built with technical assistance from Sandia National Laboratories. 
- Leverage graph data algorithms to uncover gaps and weaknesses in an organization's custody operations
- Determine risk of fraud collusion, seed compromise, key ceremony compromise, penetrative forced intrusion of storage facilities, etc...
- Store and generate the data needed for compliance reporting.  

> *Note: Sandia National Laboratories are also customers of FreeRange for digital asset risk management and procrument. Find out more about the mission of Sandia National Labs [here](https://www.sandia.gov).*   

**Security is our primary focus.** 
- FreeRange never stores, generates or has access to an organization's private keys.

The technical build overview can be found [here](/build_overview.md).

## Database schema overview

`fr-custody-api` uses a graph database model that gives a greater emphasis on relationships.

Use the API to generate self-custody models, then leverage graph-based queries to analyze risk and compliance with custody standards such as those from the CryptoCurrency Certification Consortium (C4) which can be found [here](https://cryptoconsortium.github.io/CCSS/).

Summary for Developers: 
- Nodes are the main data elements
- Nodes are connected to other nodes via relationships
- Relationships connect two nodes
- Both Nodes and Relationships can have one or more properties (i.e., attributes stored as key/value pairs)

### Nodes

#### General

| Nodes | Description | 
| --- | --- |
| `organizations` | Comprise of `key_managers` collectively managing digital assets and/or their respective cryptographic public / private key pairings |
| `accounts` | Collections of managed `wallet_addresses` belonging to the same blockchain network, grouped for accounting purposes |
| `public_keys` | Cryptographic keys assigned to `accounts`, of which private key pairings are managed by `organizations`, and are used for signing `transactions` |
| `wallet_addresses` | An address on a blockchain network used for the assignment and accounting of digital assets |

#### Key management related 

| Nodes | Description |
| --- | --- |
| `facilities` | An installation, building, or segerated space within used for the operations of organizations. Examples would be a house, bank branch, etc. Some facilities will be more hardened and have different levels of access control than others. |
| `computers`| Electronic devices used in processing and / or storing data related to key management, including `key_ceremonies`. An example would be an "air-gapped" notebook.  |
| `containers` | A physical object (ideally within a building) used for storing and securing items such as `key_storage_devices`. An example would be a safe deposit box or Faraday bag. Multiple types of `containers` can be nested within each other. |
| `entropy_sources`| Software, hardware, or analog derived (ex. deck of cards) randomness used in generating keys during `key_ceremonies` |
| `key_ceremonies` | Procedural events where `organizations` generates unique public / private root keys used to store digital assets |
| `key_managers` | Members of `organizations` that has access to, and / or helps generate public / private key pairs |
| `key_storage_devices` | A medium that stores public / private key pairs (ex. a Trezor or a piece of paper) |
| `rooms` | A physical space within a facility, such as a vault for storing and securing `key_storage_devices`, or a  windowless room for holding `key_ceremony` events. |
| `seeds` | Mnemonic phrases generated by `organizations` during a `key_ceremonies`, associated with and helps recover `wallet_addresses` tied to `key_storage_devices` |
| `seed_backups` | (M of N) physical mediums (ex. engraved metal plates) used to distribute portions of a `seed` amongst different geographical locations, allowing `organizations` to recover access to digital assets in case of `key_storage_device` failure. Idealy resistant to EMP, blast, fire, flood, etc |

#### Other

| Nodes| Description |
| --- | --- |
| `locations` | These nodes describe the name and position of a physical item using addresses, coordinates, and / or landmarks. Other nodes (example: a safe deposit box `container` or a `key_manager`) can be connected to a `location` node via the `located_at` relationship to track and visualize geographic distribution of key management systems. If multiple `containers` are nested within each other (example: a safe deposit box nested within a vault nested within a facility) the `location` node should only attach to the parent `container` |

### Relationships

#### General

| Relationships| Description |
| --- | --- |
| `assigned_to` | Connects `public_keys`, `wallet_addresses`, and other nodes to an `account`. Useful for proof-of-reserve audits  |
| `belongs_to` | Connects `key_managers`, `key_storage_devices`, `entropy_sources`, and other nodes to an `organization` |
| `beneficiary_of` | Tracks who the beneficiary of an account is (optional). Can be a customer of an `organization` or the `organization` itself |
| `located_at`| Tracks the location of other nodes. An example would be `key_storage_device` => `located_at` => `location` |
| `transaction` | Events where `wallet_addresses` sends or receives digital assets on a blockchain ledger |

#### Key management related

| Relationships| Description |
| --- | --- |
| `access` | Tracks `key_manager` access to a `location`, `container`, `key_storage_device` etc. |
| `generated` | Connects `key_generation_ceremonies` to the `seeds` that they generated  |
| `participated_in` | Connects `key_managers` to any `key_generation_ceremonies` they participated in  |
| `private_key_pair_stored_on` | Connects `public_keys` to the `key_storage_device` where the corresponding private key pair is stored. Note that the database never stores nor has access to private keys. |
| `required_for_signature` | Connects which `public_keys` are needed to sign a transaction for a `wallet_address`. Can be one `public_key` for a single signature wallet, up to 7 for a multi-sig wallet  |
| `seeded` | Connects which `seed` was used to initalize a `key_storage_device` during a `key_generation_ceremony` |
| `stored_in` | Connects `key_storage_devices` and `seed_backups` to the `containers` which they are stored in. Multiple types of `containers` can be nested within each other. An example would be `key_storage_device` => `stored_in` => a safe depost box `container` => `stored_in` => a bank vault `container`. This chaining becomes valuable when managng different layers of access control to containers through the `has_access_to` relationship. |

## Node details with API endpoints

  - [`accounts`](api_docs/accounts/accounts.md)
  - [`computers`](api_docs/computers/computers.md)
  - [`containers`](api_docs/containers/containers.md)
  - [`entropy_sources`](api_docs/entropy_sources/entropy_sources.md)
  - [`facilities`](api_docs/facilities/facilities.md)
  - [`key_ceremonies`](api_docs/key_ceremonies/key_ceremonies.md)
  - [`key_managers`](api_docs/key_managers/key_managers.md)
  - [`key_storage_devices`](api_docs/key_storage_devices/key_storage_devices.md)
  - [`locations`](api_docs/locations/locations.md)
  - [`organizations`](api_docs/organizations/organizations.md)
  - [`public_keys`](api_docs/public_keys/public_keys.md)
  - [`rooms`](api_docs/rooms/rooms.md)
  - [`seeds`](api_docs/seeds/seeds.md)
  - [`seed_backups`](api_docs/seed_backups/seed_backups.md)
  - [`wallet_addresses`](api_docs/wallet_addresses/wallet_addresses.md)
