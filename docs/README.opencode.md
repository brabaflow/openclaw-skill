# OpenClaw Skill — OpenCode Setup Guide

## Overview

This guide covers installing the OpenClaw Skill for use with OpenCode.

OpenCode discovers skills from `~/.config/opencode/skills/`. The OpenClaw Skill integrates by symlinking into this directory.

## Prerequisites

- OpenCode installed and working
- Git installed
- Terminal access

## Installation

See [.opencode/INSTALL.md](../.opencode/INSTALL.md) for step-by-step instructions.

## How it works

Once installed, OpenCode will discover the skill at startup. When you ask about OpenClaw, the agent reads the relevant documentation file from the `docs/` folder and returns exact code and configurations from the official docs.

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
ls -la ~/.config/opencode/skills/openclaw
# Should point to: /path/to/openclaw-skill/.claude/skills/openclaw
```

**Outdated docs:** Pull the latest:

```bash
cd ~/openclaw-skill && git pull
```
