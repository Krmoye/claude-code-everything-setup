# Claude Code Skill: Everything Setup

Setup [Everything](https://www.voidtools.com/) CLI (`es.exe`) for fast file search on Windows in [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

## What it does

This skill guides you through installing and configuring Everything CLI so Claude Code can use `es` for blazing-fast file searches instead of slower alternatives like `find` or `where`.

## Installation

Copy the skill to your Claude Code skills directory:

```bash
# Clone the repo
git clone https://github.com/Krmoye/claude-code-everything-setup.git
cd claude-code-everything-setup

# Copy skill to Claude Code skills directory
cp -r skills/everything-setup ~/.claude/skills/
```

Then restart Claude Code. The skill will be available as `/everything-setup`.

## Prerequisites

- **Windows** (this skill is Windows-specific)
- **[Everything](https://www.voidtools.com/)** installed and running
- **Git Bash** (for the wrapper script)

## What the skill does

When invoked, it will:

1. Check if Everything is installed and running
2. Guide you to download `es.exe` (the CLI tool)
3. Create a Git Bash wrapper script with UTF-8 encoding support
4. Verify the setup works

## Key features

- **Chinese filename support**: The wrapper script handles GBK → UTF-8 encoding conversion via `iconv`
- **PATH integration**: Adds `~/bin` to your PATH so `es` works from anywhere
- **Troubleshooting**: Built-in guidance for common issues

## Usage

In Claude Code, type:

```
/everything-setup
```

The skill will walk you through the setup process interactively.

## License

MIT
