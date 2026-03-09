# OpenClaw Skill — Codex Installation

## Quick Install

1. Clone the repository:

```bash
git clone https://github.com/brabaflow/openclaw-skill.git ~/.agents/skills/openclaw-skill
```

2. Create a symlink so Codex discovers the skill:

```bash
mkdir -p ~/.agents/skills
ln -sf ~/.agents/skills/openclaw-skill/skills/openclaw ~/.agents/skills/openclaw
```

3. Restart Codex. The skill will be discovered automatically.

## Verify

Ask Codex: "How do I configure WhatsApp with OpenClaw?"

It should consult the skill docs and return exact configuration examples from the official documentation.

## Update

```bash
cd ~/.agents/skills/openclaw-skill && git pull
```

## Uninstall

```bash
rm -rf ~/.agents/skills/openclaw ~/.agents/skills/openclaw-skill
```
