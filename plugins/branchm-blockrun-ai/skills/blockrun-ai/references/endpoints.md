# Endpoints reference — blockrun.ai

This file is auto-generated from `blockrun.ai`'s synthesized manifest at v8 combined with the public skill index (16 skills).

## Wallet Performance Analytics
Retrieves historical trading performance for a specific Polymarket wallet address, including realized/unrealized PnL, ROI, win rate, trade counts, fees, hold time, and trading style classification across multiple time windows.

### GET https://blockrun.ai/api/v1/pm/polymarket/wallet/0xdb27bf2ac5d428a9c63dbc914611036855a6c56e
**fetch-polymarket-wallet-analytics** — Returns Polymarket wallet performance analytics for a given address, including realized/unrealized PnL, volume, ROI, trade counts, win/loss metrics, trading style classification, and account age across multiple time windows.

- **When to use:** Use when an agent needs to evaluate a specific Polymarket trader's historical performance, including PnL breakdowns by time period (1d/7d/30d/all-time), win rate, trading style, and position statistics for a known wallet address.
- **Price:** free
- **Network:** eip155:8453
- **Not for:** Do not use for real-time market prices, order book data, or event resolution — this endpoint is wallet-level analytics only, not market-level data.
- **Quality score:** 92
- **Verification:** pass

### GET https://blockrun.ai/api/v1/pm/polymarket/wallet/0x4ffe49ba2a4cae123536a8af4fda48faeb609f71
**fetch-polymarket-wallet-metrics** — Returns Polymarket trading analytics for a given wallet address, including PnL, volume, win rate, trade counts, and trading style across 1-day, 7-day, 30-day, and all-time windows.

- **When to use:** Use when an agent needs to evaluate the historical trading performance of a specific Polymarket wallet, including realized/unrealized PnL, ROI, win rate, profit factor, position counts, and inferred trading style.
- **Price:** free
- **Network:** eip155:8453
- **Not for:** Do not use for real-time order book data, open market prices, or non-Polymarket wallets. Not suitable for fetching market-level statistics — this is wallet-specific analytics only.
- **Quality score:** 96
- **Verification:** pass

### GET https://blockrun.ai/api/v1/pm/polymarket/wallet/0x9174e9bFF176285E9B77022eC2e4007904495280
**fetch-polymarket-wallet-performance** — Returns Polymarket trading analytics for a wallet address, including PnL, volume, trade counts, fees, position counts, wallet age, and inferred trading style across 1-day, 7-day, 30-day, and all-time windows.

- **When to use:** Use when an agent needs to evaluate a Polymarket trader's historical performance metrics — such as realized/unrealized PnL, trade volume, win rate, fees paid, active positions, or trading style classification — for a specific wallet address.
- **Price:** free
- **Network:** eip155:8453
- **Not for:** Do not use for real-time order book data, live market prices, or open position details; use a Polymarket markets or positions API instead.
- **Quality score:** 92
- **Verification:** pass

### GET https://blockrun.ai/api/v1/pm/polymarket/wallet/0x85A66bB25955c43f13F7028F17d67172bA02e386
**fetch-polymarket-wallet-snapshot** — Returns Polymarket trading metrics, PnL, win rates, trading style classification, and position summary for a given Ethereum wallet address.

- **When to use:** Use when an agent needs to analyze a Polymarket trader's historical performance, including realized/unrealized PnL, trade counts, win rates, fees paid, and trading style across 1-day, 7-day, 30-day, and all-time windows.
- **Price:** free
- **Network:** eip155:8453
- **Not for:** Do not use for real-time market prices or order book data; use a Polymarket markets API instead. Not suitable for non-Polymarket wallets or on-chain token balances.
- **Quality score:** 88
- **Verification:** pass

## Wallet Positions
Returns current and historical Polymarket positions for a wallet, including market metadata, shares held, cost basis, current value, and PnL per position.

### GET https://blockrun.ai/api/v1/pm/polymarket/wallet/positions/0x9174e9bFF176285E9B77022eC2e4007904495280
**fetch-polymarket-wallet-positions** — Returns current and historical Polymarket positions for a given wallet address, including market metadata, shares, cost basis, current value, and PnL.

- **When to use:** Use when an agent needs to inspect a specific Polymarket wallet's open or resolved prediction market positions, including entry price, current value, unrealized/realized PnL, and market status.
- **Price:** free
- **Network:** eip155:8453
- **Not for:** Do not use for retrieving order book data, live market prices, or global market listings — use a Polymarket markets API instead. Not suitable for non-Polymarket prediction platforms.
- **Quality score:** 92
- **Verification:** pass

## Market Discovery
Browses and filters available prediction market events and listings on Polymarket and Kalshi, returning metadata such as titles, descriptions, tags, status, and resolution dates.

### GET https://blockrun.ai/api/v1/pm/polymarket/events
**fetch-polymarket-events** — Retrieves a list of Polymarket prediction market events with metadata including title, description, tags, series info, status, and resolution dates.

- **When to use:** Use when an agent needs to browse or filter active Polymarket prediction market events, retrieve event metadata (titles, descriptions, tags, open/closed status, end dates), or identify available markets for sports, politics, or other categories.
- **Price:** free
- **Network:** eip155:8453
- **Not for:** Do not use for fetching individual market order book data, current prices, or trade execution; use a dedicated Polymarket market or trade API instead.
- **Quality score:** 88
- **Verification:** pass

### GET https://blockrun.ai/api/v1/pm/kalshi/markets
**fetch-kalshi-markets** — Fetches live Kalshi prediction market listings including ticker, status, outcomes, prices, volume, and open interest for each market.

- **When to use:** Use when an agent needs current or historical Kalshi prediction market data including market status, yes/no outcome prices, volume, open interest, and settlement details for sports, politics, or other event categories.
- **Price:** free
- **Network:** eip155:8453
- **Not for:** Do not use for placing or executing trades on Kalshi markets; this endpoint is read-only market data. Do not use for non-Kalshi prediction market data.
- **Quality score:** 88
- **Verification:** pass

## Market Price History
Returns historical OHLC candlestick data for a specific Polymarket condition, enabling charting, backtesting, and analysis of price and volume over time.

### GET https://blockrun.ai/api/v1/pm/polymarket/candlesticks/0xd6591e966aebf061547ef34cdf3494ed318969887c8b7fb53f10ed5d5461a547
**fetch-polymarket-candlesticks** — Returns historical OHLC candlestick data for a Polymarket prediction market condition ID, including open/high/low/close prices, volume, trade counts, and period timestamps.

- **When to use:** Use when an agent needs historical price and volume data for a specific Polymarket condition in candlestick format, such as for charting, backtesting, or analyzing trading activity over time.
- **Price:** free
- **Network:** eip155:8453
- **Not for:** Do not use for real-time or live price feeds; this returns historical candlestick snapshots. Not suitable for fetching order book depth or current market state.
- **Quality score:** 92
- **Verification:** pass

## Market Participant Analysis
Identifies the largest position holders in a specific Polymarket market condition and provides aggregated statistics across trader cohorts segmented by trading style.

### GET https://blockrun.ai/api/v1/pm/polymarket/market/0xfbe85201ab2b4acff01cd5a3639039fc813d3448c64db081f70926bd9b9e74e9/top-holders
**fetch-polymarket-market-top-holders** — Returns the ranked list of top position holders for a specific Polymarket prediction market condition, including wallet addresses, position sizes, USD values, average prices, realized/unrealized PnL, and trade counts.

- **When to use:** Use when an agent needs to identify the largest holders in a Polymarket prediction market, analyze whale positioning, or inspect individual trader PnL and trade activity for a given market condition ID.
- **Price:** free
- **Network:** eip155:8453
- **Not for:** Do not use for retrieving overall market metadata, order book data, or price history; use a market info or price history endpoint instead.
- **Quality score:** 87
- **Verification:** pass

### GET https://blockrun.ai/api/v1/pm/polymarket/cohorts/stats
**fetch-polymarket-cohort-stats** — Returns aggregated participation, volume, PnL, win rate, and fee statistics for each Polymarket trading-style cohort (e.g. ACTIVE_TRADER, WHALE, DEGEN) over all time.

- **When to use:** Use when an agent needs to compare performance metrics across Polymarket trader cohorts, such as wallet counts, total volume, realized PnL, ROI, win rates, profit factors, and fee data segmented by trading style.
- **Price:** free
- **Network:** eip155:8453
- **Not for:** Do not use for individual wallet or position-level data; use a wallet-specific or position-level endpoint instead. Not suitable for real-time price feeds or order book data.
- **Quality score:** 92
- **Verification:** pass

## Unclustered
Skills present on the host that are not part of any synthesized capability cluster.

### GET https://blockrun.ai/api/v1/pm/polymarket/leaderboard
**fetch-polymarket-leaderboard** — Returns the global Polymarket leaderboard of smart wallets ranked by total PnL, including per-trader metrics, trading styles, and performance statistics.

- **When to use:** Use when an agent needs to identify top-performing Polymarket traders, compare realized PnL rankings, inspect win rates or profit factors, or analyze trading styles (whale, active trader, etc.) across the prediction market platform.
- **Price:** free
- **Network:** eip155:8453
- **Not for:** Do not use for individual trader lookup by address or for market-specific data; this endpoint returns only the global all-time leaderboard sorted by total PnL.
- **Quality score:** 82
- **Verification:** pass

### GET https://blockrun.ai/api/v1/pm/matching-markets/pairs
**fetch-matching-markets-pairs** — Returns all active exact-matched prediction market pairs cross-listed on Polymarket and Kalshi, with similarity scores and expiration timestamps.

- **When to use:** Use when an agent needs to identify prediction market questions that appear on both Polymarket and Kalshi simultaneously, including their condition IDs, market tickers, titles, similarity scores, and earliest expiration timestamps.
- **Price:** free
- **Network:** eip155:8453
- **Not for:** Do not use for fetching prices, order books, or liquidity data on these markets; use a market pricing or quotes endpoint instead. Not suitable for markets listed on only one platform.
- **Quality score:** 82
- **Verification:** pass
