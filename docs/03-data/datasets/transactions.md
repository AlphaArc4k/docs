---
sidebar_position: 3
---

# Transactions

Contains all transaction data, including signatures and involved accounts.

:::danger
Big data warning. See [Overview](./) for infrastructure planning.
:::

## Fields

### slot
The period of time for which each leader ingests transactions and produces a block.<br/>
Collectively, slots create a logical clock. Slots are ordered sequentially and non-overlapping, comprising roughly equal real-world time as per PoH.
### block_time
Estimated production time of a block as Unix timestamp (seconds since the Unix epoch)
### signature
A 64-byte ed25519 signature. 
Each transaction must have at least one signature for fee account. The first signature in transaction can be treated as transaction id and is used for this field.
### signer
First signer (fee payer) in the signers array.
### error (boolean)
Value indicating if the transaction failed or succeeded.
### top_level_ix_count
The total number of top-level instructions.
### compute_units
The smallest unit of measure for consumption of computational resources of the blockchain.

See [Compute Units](https://solana.com/docs/terminology#compute-units)
### fee
:::note
The Solana blockchain has a few different types of fees and costs that are incurred to use the permissionless network. These can be segmented into a few specific types:

- Transaction Fees - A fee to have validators process transactions/instructions
- Prioritization Fees - An optional fee to boost transactions processing order
:::
The *transaction fee* of the transaction.

For *prioritization fee* see `fees` dataset.
### version
`0` | `legacy`<br/>
Transaction version
### is_discarded
Fully parsed transactions are discarded and their `data` field will be empty.
### discard_reason
The reason why eth transaction was discarded e.g. it was empty, vote tx, parsed..
### data
Raw tx data as **json** if not discarded.