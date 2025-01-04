# A1 Performers

## Identifier
`a1_performers_[time interval]`

## Description
The A1 Performers (work in progress) view combines Token Metrics with the [Alpha-1 (A1) Score](../scores/a1_score.md), providing a comprehensive tool to analyze and rank tokens based on price changes and key performance indicators. This view is designed to enable efficient filtering and ordering of tokens, helping users identify those with significant **authentic activity**, market impact, or emerging trends.

## SQL Representation

```sql
a1_performers_60m as (
    SELECT
        pi.token,
        window_start,
        active_wallets,
        score,
        percentage_increase as price_increase_percent,
        tm.sol_volume,
        tm.buy_volume,
        tm.sell_volume,
        tm.avg_trade_size,
        tm.unique_buyers,
        tm.buy_count,
        tm.sell_count
    FROM price_increases_60m pi join token_metrics tm on tm.token = pi.token
    WHERE score > 10 and pi.token not in (
      'EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v', -- USDC
      'Es9vMFrzaCERmJfrF4H2FYD4KCoNkY11McCe8BenwNYB' -- USDT
    )
    ORDER BY score desc, percentage_increase desc
)
```

## Fields

For fields refer to token metrics and price increase view.