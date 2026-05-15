<p align="center">
  <img src="https://raw.githubusercontent.com/Dexter-DAO/dexter-x402-sdk/main/assets/dexter-wordmark.svg" alt="Dexter" width="360">
</p>

<h1 align="center">Composed Skills</h1>

<p align="center">
  <strong>Claude Code plugin bundles synthesized from x402 hosts.</strong><br>
  One repo, one marketplace, every published skill across x402gle.
</p>

<p align="center">
  <a href="https://x402gle.com/skills"><img src="https://img.shields.io/badge/browse-x402gle.com%2Fskills-blueviolet" alt="Browse"></a>
  <a href="https://x402.org"><img src="https://img.shields.io/badge/protocol-x402_v2-00FF88" alt="x402"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="MIT"></a>
</p>

<p align="center">
  <a href="https://x402gle.com/skills"><strong>Browse Skills</strong></a>&nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="https://x402gle.com"><strong>x402gle</strong></a>&nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="https://dexter.cash"><strong>Dexter</strong></a>
</p>

---

## Install a Skill

Add this repo as a Claude Code marketplace, then install any plugin from it:

```bash
/plugin marketplace add Dexter-DAO/composed-skills
/plugin install <owner>-<slug>@x402gle
```

Or browse and install via x402gle.com:

1. Visit [x402gle.com/skills](https://x402gle.com/skills)
2. Click any composed skill
3. Hit the **Install** button. Copy the slash commands or click the `claude-cli://` deep link.

---

## What's in Here

Every published composed skill lives under `plugins/<owner>-<slug>/` as a self-contained Claude Code plugin. The aggregate catalog lives at [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json).

Each plugin contains:

```
plugins/<owner>-<slug>/
├── .claude-plugin/
│   └── plugin.json
├── README.md
├── LICENSE
└── skills/
    └── <slug>/
        ├── SKILL.md
        ├── references/endpoints.md
        └── assets/output-template.md
```

A composed skill is **synthesized** by x402gle from one or more x402 hosts' manifests (capability clusters, workflows, pricing, provenance) and rendered into the Anthropic Claude Code plugin format. The composer authors the workflow once; agents install and use it forever.

---

## What's a Composed Skill?

An x402 host (like `blockrun.ai`) exposes paid endpoints. x402gle synthesizes a manifest describing what each host does: positioning, capability clusters, multi-step workflows. A **composed skill** wraps one or more of those manifests into a Claude Code plugin that an agent installs once and uses forever.

The user journey:

1. **Find.** `x402gle.com/skills` lists every public composed skill, ranked by installs and quality.
2. **Install.** One paste (`/plugin marketplace add` + `/plugin install`) or one click (`claude-cli://` deep link).
3. **Use.** Claude reads the skill's `SKILL.md` and calls the underlying x402 endpoints with auto-payment via OpenDexter.

---

## Composing a New Skill

Composed skills are authored through the OpenDexter MCP server. From inside Claude Code with [OpenDexter](https://github.com/Dexter-DAO/opendexter-ide) installed:

```
Compose a skill that wraps blockrun.ai's Polymarket analytics.
```

The agent calls `x402_compose_skill`, which renders the bundle, persists it to x402gle, and publishes here automatically. Once published, the skill is installable everywhere.

To make it public (discoverable on `x402gle.com/skills`):

```
Promote my blockrun-ai skill to public.
```

---

## Provenance

Every plugin in this repo has a [provenance stamp](https://x402gle.com/docs/provenance) in its `SKILL.md` frontmatter:

- `host_provenance: merchant_reviewed`. The host owner has reviewed and approved the synthesized manifest.
- `host_provenance: merchant_edited`. The host owner has edited the manifest directly.
- `host_provenance: ai_authored_reviewed`. x402gle's synthesizer authored it; the host owner has explicitly accepted.
- `host_provenance: ai_authored_unreviewed`. x402gle's synthesizer authored it; no human review yet.

Each plugin also pins to the specific manifest version it was composed against. When the upstream host evolves, x402gle flags the composed skill as drifted so the composer can review and republish.

---

## License

MIT for the bundle text and boilerplate in this repository. Endpoint authors' terms apply to the actual API calls each skill makes.
