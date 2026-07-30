---
name: everything-setup
description: Setup Everything CLI (es.exe) for fast file search on Windows. Use when user asks to configure Everything integration, install es.exe, or set up fast file search for Claude Code.
---

# Everything CLI Setup

Guide the user through installing and configuring Everything CLI (`es.exe`) for fast file search in Claude Code on Windows.

## Prerequisites Check

Before starting, verify:
1. Everything is installed: check `C:\Program Files\Everything\Everything.exe`
2. Everything is running: `tasklist | grep -i everything`

If not installed, direct user to: https://www.voidtools.com/downloads/

## Setup Steps

### Step 1: Download es.exe

`es.exe` is NOT bundled with Everything — it's a separate download.

Direct user to: https://www.voidtools.com/downloads/#cli

Download the **ES Command-line Interface** zip, extract `es.exe`, and place it in `C:\Program Files\Everything\`.

### Step 2: Create Wrapper Script (Git Bash)

Git Bash needs a wrapper script to handle PATH and encoding. Create `~/bin/es`:

```bash
mkdir -p ~/bin
cat > ~/bin/es << 'EOF'
#!/bin/bash
"/c/Program Files/Everything/es.exe" "$@" | iconv -f GBK -t UTF-8 2>/dev/null
EOF
chmod +x ~/bin/es
```

Add `~/bin` to PATH permanently:
```bash
echo 'export PATH="$HOME/bin:$PATH"' >> ~/.bashrc
```

### Step 3: Verify

```bash
~/bin/es "test" -n 5
```

Should return file paths with Chinese characters displayed correctly.

### Step 4: Save to Claude Code Memory

Write a memory file so Claude Code knows to use `es` for file search in future sessions.

## Troubleshooting

- **Chinese garbled text**: The wrapper script pipes through `iconv -f GBK -t UTF-8`. If still garbled, check if iconv is available: `which iconv`
- **es.exe not found**: Verify file exists at `C:\Program Files\Everything\es.exe` and wrapper script at `~/bin/es`
- **Permission denied**: Run terminal as administrator, or check file permissions on es.exe
