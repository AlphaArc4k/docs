# Token Metrics

Most popular metrics used by token trackers: volume, buy and sell count...

## Description

The Token Metrics dataset offers a detailed view of token trading activity on Solana, providing essential insights into market dynamics. 
In addition to standard metrics like volume and transaction counts, AlphaArc includes **Unique Signers** and **Average Trade Size** as enhanced analytics fields to provide deeper insights into user behavior and trading patterns.

## Fields

### token
The identifier (CA / mint address) of the token being analyzed.
### sol_volume
The total trading volume denominated in SOL during the interval: `buy_volume`+ `sell_volume`
### buy_volume
The total value of tokens purchased during the interval, measured in SOL.
### sell_volume
The total value of tokens sold during the interval, measured in SOL.
### avg_trade_size 
*(Additional Metric)*

- The average size of trades for the token within the interval.
- Calculated as the total volume divided by the number of trades.
- Provides insight into typical trade behavior, such as whale vs. retail activity.
### unique_signers 
*(Additional Metric)*
- The count of unique wallets interacting with the token during the interval.
- Includes buyers, sellers, and other participants.
- Useful for assessing the diversity of token engagement.
### unique_buyers 
The number of **distinct** signers that purchased the token during the interval.
### buy_count
The total number of buy transactions for the token within the interval.
### sell_count
The total number of sell transactions for the token within the interval.