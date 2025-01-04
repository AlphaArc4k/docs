# Programs

Program invocations and instruction data.

:::danger
Big data warning. See [Overview](./) for infrastructure planning.
:::

## Fields

### signature
A 64-byte ed25519 signature. 
Each transaction must have at least one signature for fee account. The first signature in transaction can be treated as transaction id and is used for this field.
### ix_index
The instruction index starting at 0.
### program_id
The public key of the Solana program being invoked.
### ix_type
The Instruction Type indicates the type of operation being performed within the program. 
This is typically encoded in the instruction data and determines the program-specific function call.
### parsed (boolean)
Value indicating if the instruction could be parsed successfully.
### has_error (boolean)
Value indicating if the transaction failed or succeeded.