# pi-skills

A collection of skills for [pi-coding-agent](https://github.com/badlogic/pi-mono/tree/main/packages/coding-agent), compatible with Claude Code, Codex CLI, Amp, and Droid.

## Installation

### pi-coding-agent

```bash
# User-level (available in all projects)
git clone https://github.com/jolantis/pi-skills ~/.pi/agent/skills/pi-skills

# Or project-level
git clone https://github.com/jolantis/pi-skills .pi/skills/pi-skills
```

### Codex CLI

```bash
git clone https://github.com/jolantis/pi-skills ~/.codex/skills/pi-skills
```

### Amp

Amp finds skills recursively in toolboxes:

```bash
git clone https://github.com/jolantis/pi-skills ~/.config/amp/tools/pi-skills
```

### Droid (Factory)

```bash
# User-level
git clone https://github.com/jolantis/pi-skills ~/.factory/skills/pi-skills

# Or project-level
git clone https://github.com/jolantis/pi-skills .factory/skills/pi-skills
```

### Claude Code

Claude Code only looks one level deep for `SKILL.md` files, so each skill folder must be directly under the skills directory. Clone the repo somewhere, then symlink individual skills:

```bash
# Clone to a convenient location
git clone https://github.com/jolantis/pi-skills ~/pi-skills

# Symlink individual skills (user-level)
mkdir -p ~/.claude/skills
ln -s ~/pi-skills/browser-tools ~/.claude/skills/browser-tools
ln -s ~/pi-skills/transcribe ~/.claude/skills/transcribe
ln -s ~/pi-skills/youtube-transcript ~/.claude/skills/youtube-transcript

# Or project-level
mkdir -p .claude/skills
ln -s ~/pi-skills/browser-tools .claude/skills/browser-tools
ln -s ~/pi-skills/transcribe .claude/skills/transcribe
ln -s ~/pi-skills/youtube-transcript .claude/skills/youtube-transcript
```

## Available Skills

| Skill | Description |
|-------|-------------|
| [browser-tools](browser-tools/SKILL.md) | Interactive browser automation via Chrome DevTools Protocol |
| [transcribe](transcribe/SKILL.md) | Speech-to-text transcription via Groq Whisper API |
| [youtube-transcript](youtube-transcript/SKILL.md) | Fetch YouTube video transcripts |

## Skill Format

Each skill follows the pi/Claude Code format:

```markdown
---
name: skill-name
description: Short description shown to agent
---

# Instructions

Detailed instructions here...
Helper files available at: {baseDir}/
```

The `{baseDir}` placeholder is replaced with the skill's directory path at runtime.

## Requirements

Some skills require additional setup. Generally, the agent will walk you through that. But if not, here you go:

- **browser-tools**: Requires Chrome and Node.js. Run `npm install` in the skill directory.
- **transcribe**: Requires curl and a Groq API key.
- **youtube-transcript**: Requires Node.js. Run `npm install` in the skill directory.

## License

MIT
