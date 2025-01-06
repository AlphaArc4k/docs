# Tokens

SPL tokens.

## Fields

### signer
 Refers to the account(s) that authorize a transaction. Signers are typically required to approve operations such as minting, burning, or transferring tokens.

### mint
The mint account for the token, linking the metadata to a specific SPL token.

### factory
Program that created the token.
### create_tx
Signature of the tx where token was created.
### create_block_time
Refers to the timestamp of the block in which the token mint account was created. The block time is expressed in Unix epoch time (seconds since January 1, 1970).
### create_slot
Refers to the slot number associated with the block when the token mint account was created.
### initial_supply
Refers to the first batch of tokens minted after the token’s mint account is created.
### supply
Represents the total supply of tokens in circulation. Stored as an unsigned 64-bit integer. Updated automatically during minting (increase supply) or burning (decrease supply).

### decimals
Specifies the number of decimal places the token supports (e.g., 6 for USDC).

### name
The human-readable name of the token (e.g., “USDC”, “Wrapped Bitcoin”).

### symbol
The ticker symbol of the token (e.g., “USDC”, “WBTC”). Maximum length: 10 characters.

### uri
A URL pointing to off-chain metadata, often stored on a decentralized storage system (e.g., Arweave, IPFS). Contains additional details like the token’s logo, description, and more.
