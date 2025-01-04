# Sol Transfers

Native sol transfers.

## Fields

### slot
The period of time for which each leader ingests transactions and produces a block.<br/>
Collectively, slots create a logical clock. Slots are ordered sequentially and non-overlapping, comprising roughly equal real-world time as per PoH.
### block_time
Estimated production time of a block as Unix timestamp (seconds since the Unix epoch).
### signature
A 64-byte ed25519 signature. 
Each transaction must have at least one signature for fee account. The first signature in transaction can be treated as transaction id and is used for this field.
### src
Sender (source) wallet address.
### dst
Receiver (destination) wallet address.
### lamports
Lamports sent / received.
### sol
Sol sent / received.