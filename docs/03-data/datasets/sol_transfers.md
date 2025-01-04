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
The public key of the sender’s account. This account must hold the SOL to be transferred. It is also the signer of the transaction, authorizing the transfer.

### dst
The public key of the recipient’s account. This account will receive the transferred SOL.

### lamports
Amount of Lamports transferred.
### sol
Amount of SOL transferred.