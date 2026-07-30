# Claude Code Skills: Everything Integration

[Everything](https://www.voidtools.com/) CLI integration for [Claude Code](https://docs.anthropic.com/en/docs/claude-code) on Windows — blazing-fast file search.

## Included Skills

| Skill | Command | Purpose |
|-------|---------|---------|
| **everything-setup** | `/everything-setup` | Install and configure `es.exe` |
| **everything** | `/everything` | Quick reference for using `es` commands |

## Installation

```bash
git clone https://github.com/Krmoye/claude-code-everything.git
cd claude-code-everything

# Copy both skills to Claude Code
cp -r skills/* ~/.claude/skills/
```

Then restart Claude Code.

## Prerequisites

- **Windows**
- **[Everything](https://www.voidtools.com/)** installed and running
- **Git Bash** (for the wrapper script)

## Quick Start

1. Run `/everything-setup` to install and configure `es.exe`
2. Then use `/everything` as a reference for search commands

## Search Examples

```
es "keyword"                    # Basic search
es ext:pdf                      # By extension
es ext:ppt|pptx                 # Multiple extensions
es -path "C:\Users\Desktop" "report" -n 10  # Limit to directory
es ext:xlsx -s "date modified"  # Sort by date
```

## License

MIT
