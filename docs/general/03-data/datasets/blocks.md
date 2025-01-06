---
sidebar_position: 2
---

# Blocks

Includes details of all blocks produced within the interval.

## Fields

### slot
The period of time for which each leader ingests transactions and produces a block.<br/>
Collectively, slots create a logical clock. Slots are ordered sequentially and non-overlapping, comprising roughly equal real-world time as per PoH.
### block_time
Estimated production time of a block as Unix timestamp (seconds since the Unix epoch).
### parent_slot
Slot of the block's parent.
### transaction_count
Total number of transactions within the block.