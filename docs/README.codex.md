# OpenClaw Skill — Codex Setup Guide

## Overview

This guide covers installing the OpenClaw Skill for use with Codex.

Codex has native skill discovery that scans `~/.agents/skills/` at startup. The OpenClaw Skill integrates by symlinking into this directory.

## Prerequisites

- Codex installed and working
- Git installed
- Terminal access

## Installation

See [.codex/INSTALL.md](../.codex/INSTALL.md) for step-by-step instructions.

## How it works

Once installed, Codex will discover the skill at startup. When you ask about OpenClaw, the agent reads the relevant documentation file from the `docs/` folder and returns exact code and configurations from the official docs.

## Skill structure

The skill contains 20 documentation files covering 333 pages:

- Core concepts, installation, gateway configuration
- Chat channels (WhatsApp, Telegram, Discord, etc.)
- Model providers (Anthropic, OpenAI, Ollama, etc.)
- Agent tools, automation, plugins
- Platform-specific guides (macOS, iOS, Android, Linux, Windows)
- Cloud deployment guides
- CLI reference (47 pages)
- Templates, security, troubleshooting

## Troubleshooting

**Skill not detected:** Make sure the symlink points to the correct path:

```bash
ls -la ~/.agents/skills/openclaw
# Should point to: /path/to/openclaw-skill/.claude/skills/openclaw
```

**Outdated docs:** Pull the latest:

```bash
cd ~/.agents/skills/openclaw-skill && git pull
```
