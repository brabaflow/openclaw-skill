# OpenClaw Skill

**The complete OpenClaw documentation as a skill for your coding agent.**

Ask your agent anything about OpenClaw — gateway config, channel setup, CLI commands, deployment — and get answers with **exact code and configs** straight from the official docs. No hallucinated flags, no invented keys.

Created by **Michel Costa**, co-founder of [Brabaflow — AI-Native Agency](https://www.brabaflow.ai/).

## How it works

When you ask your coding agent about OpenClaw, the skill kicks in automatically. Instead of guessing or relying on training data, it looks up the **official documentation** (333 pages from docs.openclaw.ai, copied verbatim) and gives you the real answer.

The skill is organized into 20 domain files. A router (`SKILL.md`) maps your question to the right domain, reads the original docs, and returns exact code blocks, configuration snippets, and CLI commands — unchanged from the source.

**No summaries. No paraphrasing. No creative interpretation of config keys.**

## Sponsorship

If this skill has saved you time and you're so inclined, I'd appreciate it if you'd consider supporting the project with a star or sharing it with the OpenClaw community.

Thanks!
— Michel

## Installation

> **Note:** Installation differs by platform. Claude Code and Cursor have built-in plugin systems. Codex and OpenCode require manual setup.

### Claude Code (via Plugin Marketplace)

In Claude Code, register the marketplace first:

```
/plugin marketplace add brabaflow/openclaw-skill-marketplace
```

Then install the plugin:

```
/plugin install openclaw-skill@openclaw-skill-marketplace
```

### Claude Code (manual)

```bash
git clone https://github.com/brabaflow/openclaw-skill.git /tmp/openclaw-skill
mkdir -p your-project/.claude/skills
cp -r /tmp/openclaw-skill/skills/openclaw your-project/.claude/skills/
rm -rf /tmp/openclaw-skill
```

### Cursor (via Plugin Marketplace)

In Cursor Agent chat:

```
/plugin-add openclaw-skill
```

### Codex

Tell Codex:

```
Fetch and follow instructions from https://raw.githubusercontent.com/brabaflow/openclaw-skill/refs/heads/main/.codex/INSTALL.md
```

Detailed docs: [docs/README.codex.md](docs/README.codex.md)

### OpenCode

Tell OpenCode:

```
Fetch and follow instructions from https://raw.githubusercontent.com/brabaflow/openclaw-skill/refs/heads/main/.opencode/INSTALL.md
```

Detailed docs: [docs/README.opencode.md](docs/README.opencode.md)

### Verify Installation

Start a new session and ask something about OpenClaw (e.g., "How do I set up WhatsApp with OpenClaw?" or "Show me the Gateway config for Anthropic"). The agent should consult the skill docs and respond with exact configuration examples.

## What's Inside

### Documentation Library

All files are in `skills/openclaw/docs/`. Each contains **verbatim** documentation from docs.openclaw.ai.

#### Core

| File | Pages | Covers |
|------|-------|--------|
| `01-core-concepts.md` | 42 | Architecture, agent loop, sessions, memory, compaction, streaming, models |
| `02-installation.md` | 11 | Docker, Podman, Nix, Ansible, Bun, Node.js, updating, migrating |
| `03-gateway.md` | 31 | WebSocket protocol, auth, secrets, health, sandboxing, APIs, discovery |

#### Channels & Providers

| File | Pages | Covers |
|------|-------|--------|
| `04-channels.md` | 29 | WhatsApp, Telegram, Discord, Slack, Signal, iMessage, Matrix, IRC, and 12 more |
| `05-providers.md` | 29 | Anthropic, OpenAI, Bedrock, Ollama, OpenRouter, Mistral, MiniMax, and 20 more |

#### Tools & Automation

| File | Pages | Covers |
|------|-------|--------|
| `06-tools.md` | 31 | Browser control, exec, skills, PDF, web tools, sub-agents, Lobster, TTS |
| `07-automation.md` | 8 | Cron jobs, heartbeat, hooks, webhooks, Gmail Pub/Sub, polls |
| `08-plugins.md` | 6 | Plugin system, manifest, SDK, Voice Call, OpenProse |

#### Platforms & Deployment

| File | Pages | Covers |
|------|-------|--------|
| `09-nodes.md` | 8 | Audio, camera, talk mode, voice wake, location, media understanding |
| `10-platforms-macos.md` | 20 | macOS app, menu bar, canvas, permissions, IPC, Peekaboo |
| `11-platforms-mobile.md` | 2 | iOS, Android |
| `12-platforms-desktop.md` | 2 | Linux, Windows/WSL2 |
| `13-deploy.md` | 12 | Hetzner, GCP, Fly.io, Railway, Render, DigitalOcean, Oracle Cloud, Raspberry Pi |

#### Reference

| File | Pages | Covers |
|------|-------|--------|
| `14-cli.md` | 47 | Every `openclaw` CLI command |
| `15-web-uis.md` | 4 | WebChat, Dashboard, TUI |
| `16-security.md` | 2 | Threat model (MITRE ATLAS) |
| `17-templates.md` | 8 | AGENTS.md, IDENTITY.md, SOUL.md, USER.md, TOOLS.md, HEARTBEAT.md |
| `18-reference.md` | 15 | Wizard, token use, prompt caching, session management, RPC adapters |
| `19-troubleshooting.md` | 8 | FAQ, debugging, diagnostics, environment variables |
| `20-experiments.md` | 10 | Design docs, proposals, research notes |

**Total: 333 pages | 20 files | 2.3 MB**

## The Workflow

1. **You ask a question** — "How do I configure Discord for OpenClaw?"
2. **The router identifies the domain** — Discord belongs to `04-channels.md`
3. **The agent reads the original documentation** — opens the file, finds the exact section
4. **You get the real answer** — with code blocks, config examples, and CLI commands identical to the official docs

Every `docs/` file has `<!-- SOURCE: url -->` comments so you can trace any answer back to the original page.

## Rules

The skill enforces strict accuracy:

1. **NEVER paraphrase code blocks or configuration examples** — verbatim only
2. **NEVER invent configuration keys or CLI flags** — only what's in the docs
3. **Always show full context** for config examples (surrounding keys, comments)
4. **Always include caveats** — version requirements, platform limitations
5. **Say "I don't know"** if the answer isn't in the docs — no guessing
6. **Always cite the source** — which doc section the answer came from
7. **Exact CLI syntax** — always from the docs, never improvised

## Philosophy

- **Accuracy over convenience** — Real documentation beats creative answers
- **Verbatim over summary** — Code configs must be exact, not paraphrased
- **Honesty over helpfulness** — "Not in the docs" is better than a wrong answer
- **Source traceability** — Every answer should be verifiable against the original docs

## Usage Examples

| Question | Doc consulted |
|----------|--------------|
| "Install OpenClaw with Docker" | `02-installation.md` |
| "Set up WhatsApp Cloud API" | `04-channels.md` |
| "Configure Anthropic as provider" | `05-providers.md` |
| "Create a Gateway cron job" | `07-automation.md` |
| "Deploy to Fly.io" | `13-deploy.md` |
| "How does the exec tool work?" | `06-tools.md` |
| "CLI command to list channels" | `14-cli.md` |
| "Create a plugin" | `08-plugins.md` |
| "Gateway won't connect" | `19-troubleshooting.md` |
| "Configure AGENTS.md" | `17-templates.md` |

## Updating

If installed via plugin marketplace:

```
/plugin update openclaw-skill
```

If installed manually, pull the latest and re-copy:

```bash
cd /path/to/openclaw-skill && git pull
cp -r skills/openclaw /path/to/your-project/.claude/skills/
```

## Documentation Source

Extracted from **[docs.openclaw.ai](https://docs.openclaw.ai)** on March 9, 2026.

## Credits

Created by **Michel Costa**, co-founder of **[Brabaflow — AI-Native Agency](https://www.brabaflow.ai/)**.

Brabaflow transforms companies into AI-First enterprises through diagnosis, training, and implementation of AI agents. Based in Alphaville, SP, Brazil.

- [brabaflow.ai](https://www.brabaflow.ai/)
- [Brabaflow on LinkedIn](https://www.linkedin.com/company/brabaflow)
- [Michel Costa on LinkedIn](https://www.linkedin.com/in/sigamichelcosta)

## Contributing

1. Fork the repository
2. Add or update documentation files in `skills/openclaw/docs/`
3. Update the router index in `skills/openclaw/SKILL.md` if adding new domains
4. Submit a PR

## License

MIT License — see [LICENSE](LICENSE) file for details.

The documentation content belongs to the [OpenClaw](https://openclaw.ai) project (MIT licensed). This skill is a packaging layer for use with coding agents.
