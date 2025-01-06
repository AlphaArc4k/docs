# Token Transfers

SPL Token transfers.

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
The public key of the source token (where the tokens will be transferred from). This is an associated token account (ATA) linked to the sender’s wallet and the specific token.

### dst
The public key of the destination token account (where the tokens will be sent). This is also an ATA linked to the recipient’s wallet for the specific token.

### from_acc
The public key of the owner of the source token account (usually the sender’s wallet address).
This account must sign the transaction to authorize the transfer.

### to_acc
The token account where tokens will be received.

### amount
 The amount of tokens to transfer, typically in smallest unit (e.g., lamports for SPL tokens). \
 Example: If transferring 1 token and the token has 6 decimals, the amount would be 1_000_000.

### token
The public key of the token. 
### decimals
Specifies the number of decimal places the token supports (e.g., 6 for USDC).
### authority
The authority that has permission to transfer tokens from a token account.
Typically, this is the owner of the source token account.
