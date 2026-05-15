---
name: Blockrun
version: 1.0.0
description: >-
  blockrun.ai is a prediction market data host focused on Polymarket and Kalshi. It serves agents
  that need to analyze trader performance, browse available markets, inspect market price history,
  or compare cohort-level statistics. Its primary strength is wallet analytics across multiple time
  windows (1d/7d/30d/all-time) and cross-market coverage spanning both Polymarket and Kalshi. It
  does not support order placement, live order book depth, or non-prediction-market on-chain data.
authored_by: x402gle
authored_at: '2026-05-15T17:00:46.293Z'
pinned_host_version: 8
host_provenance: ai_authored_unreviewed
host: blockrun.ai
slug: blockrun-ai
---

# Blockrun

blockrun.ai is a prediction market data host focused on Polymarket and Kalshi. It serves agents that need to analyze trader performance, browse available markets, inspect market price history, or compare cohort-level statistics. Its primary strength is wallet analytics across multiple time windows (1d/7d/30d/all-time) and cross-market coverage spanning both Polymarket and Kalshi. It does not support order placement, live order book depth, or non-prediction-market on-chain data.

## What this skill does
blockrun.ai provides read-only analytics and data feeds for Polymarket and Kalshi prediction markets. It covers wallet-level performance metrics, market-level data (events, candlesticks, top holders), cohort statistics, and Kalshi market listings. All endpoints are data retrieval only — no trade execution is supported.

## When to use it
Use blockrun.ai when an agent needs Polymarket wallet analytics (PnL, win rate, trading style, position history) or wants to browse Polymarket events and Kalshi market listings. It is the right choice for profiling individual traders, identifying market whales, analyzing candlestick price history, or comparing cohort-level statistics. Do not use blockrun.ai for live order book depth, real-time bid/ask prices, or trade execution on either platform — use the native Polymarket CLOB API or Kalshi trading API for those needs. It is also not suitable for on-chain token balances, DeFi positions, or any prediction market outside Polymarket and Kalshi.

## Workflows

### Trader Profile Deep Dive
Use when an agent needs to build a comprehensive profile of a Polymarket trader, combining their open positions with historical performance metrics.

Steps:
1. **fetch-polymarket-wallet-analytics** — Retrieve the wallet's historical PnL, ROI, win rate, trade counts, and trading style classification across all time windows.
2. **fetch-polymarket-wallet-positions** — Fetch the wallet's current open and resolved positions to see what markets they are actively exposed to.

### Market Whale Analysis
Use when an agent needs to identify top holders in a Polymarket market and then evaluate the trading quality of those whale wallets.

Steps:
1. **fetch-polymarket-market-top-holders** — Retrieve the ranked list of largest position holders for a given market condition ID.
2. **fetch-polymarket-wallet-analytics** — For one or more top holder wallet addresses, fetch detailed performance analytics to assess their historical accuracy and trading style.

### Market Context and Price History
Use when an agent needs to discover available Polymarket events and then analyze the price history of a specific market condition within those events.

Steps:
1. **fetch-polymarket-events** — Browse available Polymarket events to identify relevant markets and obtain condition IDs.
2. **fetch-polymarket-candlesticks** — Fetch historical OHLC candlestick data for the identified condition ID to analyze price and volume trends.

### Cohort Benchmarking for a Wallet
Use when an agent needs to evaluate how a specific wallet's performance compares to its trading style cohort across the broader Polymarket population.

Steps:
1. **fetch-polymarket-wallet-analytics** — Retrieve the target wallet's performance metrics and trading style classification.
2. **fetch-polymarket-cohort-stats** — Fetch aggregated cohort statistics to benchmark the wallet's PnL, win rate, and volume against others in the same trading style group.

## Capabilities

- **Wallet Performance Analytics**
  Retrieves historical trading performance for a specific Polymarket wallet address, including realized/unrealized PnL, ROI, win rate, trade counts, fees, hold time, and trading style classification across multiple time windows.
  Skills: fetch-polymarket-wallet-analytics, fetch-polymarket-wallet-metrics, fetch-polymarket-wallet-performance, fetch-polymarket-wallet-snapshot
- **Wallet Positions**
  Returns current and historical Polymarket positions for a wallet, including market metadata, shares held, cost basis, current value, and PnL per position.
  Skills: fetch-polymarket-wallet-positions
- **Market Discovery**
  Browses and filters available prediction market events and listings on Polymarket and Kalshi, returning metadata such as titles, descriptions, tags, status, and resolution dates.
  Skills: fetch-polymarket-events, fetch-kalshi-markets
- **Market Price History**
  Returns historical OHLC candlestick data for a specific Polymarket condition, enabling charting, backtesting, and analysis of price and volume over time.
  Skills: fetch-polymarket-candlesticks
- **Market Participant Analysis**
  Identifies the largest position holders in a specific Polymarket market condition and provides aggregated statistics across trader cohorts segmented by trading style.
  Skills: fetch-polymarket-market-top-holders, fetch-polymarket-cohort-stats

## Provenance
This skill was synthesized by x402gle from `blockrun.ai`'s manifest at v8 (provenance: ai_authored_unreviewed).
Current host manifest: https://x402gle.com/servers/blockrun.ai
