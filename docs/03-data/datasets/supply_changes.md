# Supply Changes

Burn and mint events.

## Fields

### signature
A 64-byte ed25519 signature. 
Each transaction must have at least one signature for fee account. The first signature in transaction can be treated as transaction id and is used for this field.
### ix_index
Instruction Index specifies the type of instruction being executed within the SPL Token Program.

### mint
 The mint account associated with the SPL token. This account tracks the total supply and is required for any minting or burning operation.

### amount
The number of tokens to mint or burn, specified in the smallest unit (e.g., lamports

### authority (e.g., mintAuthority)
 Must sign the transaction to authorize changes.
