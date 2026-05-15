# Blockrun

blockrun.ai is a prediction market data host focused on Polymarket and Kalshi. It serves agents that need to analyze trader performance, browse available markets, inspect market price history, or compare cohort-level statistics. Its primary strength is wallet analytics across multiple time windows (1d/7d/30d/all-time) and cross-market coverage spanning both Polymarket and Kalshi. It does not support order placement, live order book depth, or non-prediction-market on-chain data.

Composed by [x402gle](https://x402gle.com) from `blockrun.ai`'s synthesized manifest at v8 (provenance: ai_authored_unreviewed).

## Install

Save this bundle to disk, then from inside Claude Code:

```
/skill install ./blockrun-ai
```

Or drop the bundle into `~/.claude/skills/` and restart Claude Code.

## What this skill calls

This skill calls paid endpoints on `blockrun.ai`. Endpoint authors' terms apply to the actual API calls. See [SKILL.md](./plugins/blockrun-ai/skills/blockrun-ai/SKILL.md) for the full workflow and [references/endpoints.md](./plugins/blockrun-ai/skills/blockrun-ai/references/endpoints.md) for endpoint details.

## License

The bundle text and boilerplate are MIT-licensed. See `LICENSE`.
