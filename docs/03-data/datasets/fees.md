---
sidebar_position: 5
---

# Fees

Priority fees and compute units.

## Fields

### slot
The period of time for which each leader ingests transactions and produces a block.<br/>
Collectively, slots create a logical clock. Slots are ordered sequentially and non-overlapping, comprising roughly equal real-world time as per PoH.
### block_time
Estimated production time of a block as Unix timestamp (seconds since the Unix epoch).
### signature
A 64-byte ed25519 signature. 
Each transaction must have at least one signature for fee account. The first signature in transaction can be treated as transaction id and is used for this field.
### compute_unit_limit
Each transaction has a maximum number of compute units (CU) it can consume called the "compute unit limit".
A transaction can request a more specific and optimal compute unit limit by including a single SetComputeUnitLimit instruction. 
Either a higher or lower limit which is captured bz this field.
### priority_fee
As part of the Compute Budget, the runtime supports transactions paying an optional fee known as a "prioritization fee". Paying this additional fee helps boost how a transaction is prioritized against others when processing, resulting in faster execution times.
A transaction's prioritization fee is calculated by multiplying its compute unit limit by the compute unit price.
This field captures the *transaction's prioritization fee*.