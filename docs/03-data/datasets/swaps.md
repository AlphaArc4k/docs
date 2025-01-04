---
sidebar_position: 4
---

# Swaps

Token swap data extracted from decentralized exchanges.

## Fields

### slot
The period of time for which each leader ingests transactions and produces a block.<br/>
Collectively, slots create a logical clock. Slots are ordered sequentially and non-overlapping, comprising roughly equal real-world time as per PoH.
### block_time
Estimated production time of a block as Unix timestamp (seconds since the Unix epoch).
### signer
### signature
### error (boolean)
### dex
TODO see parsed dexes
### swap_type
`Buy | Sell | Token`
- **Buy:** SOL for token swap.
- **Sell:** Token for SOL swap.
- **Token:** Token for token swap.
### token_in
Pool perspective: the token swapped into the pool.
If `swap_type` is `Buy` the swapped in token will be Wrapped SOL (`So11111111111111111111111111111111111111112`).
### amount_in
Token amount put into the pool.
### token_out
Pool perspective: the token swapped out of the pool.
If `swap_type` is `Sell` the swapped out token will be Wrapped SOL (`So11111111111111111111111111111111111111112`)
### amount_out
Token amount removed from pool.
### token
Helper field to avoid `CASE .. WHEN..`.
Will be set to the token in a `swap_type` `Buy | Sell` swap or `NULL` for `Token` swaps.