# OpenClaw Skill — OpenCode Installation

## Quick Install

1. Clone the repository:

```bash
git clone https://github.com/brabaflow/openclaw-skill.git ~/openclaw-skill
```

2. Symlink the skill into OpenCode's skills directory:

```bash
mkdir -p ~/.config/opencode/skills
ln -sf ~/openclaw-skill/skills/openclaw ~/.config/opencode/skills/openclaw
```

3. Restart OpenCode. The skill will be discovered automatically.

## Verify

Ask OpenCode: "How do I configure WhatsApp with OpenClaw?"

It should consult the skill docs and return exact configuration examples from the official documentation.

## Update

```bash
cd ~/openclaw-skill && git pull
```

## Uninstall

```bash
rm -f ~/.config/opencode/skills/openclaw
rm -rf ~/openclaw-skill
```
