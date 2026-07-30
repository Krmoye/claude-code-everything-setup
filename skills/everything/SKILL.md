---
name: everything
description: Use Everything CLI (es) for fast file search on Windows. Use when user asks to find, search, or locate files by name, extension, path, or keyword. Replaces find, where, and manual directory traversal.
---

# Everything File Search

Use `es` command for fast file searching. Much faster than Windows built-in search, `find`, or `where`.

## Quick Reference

| Task | Command |
|------|---------|
| Basic search | `es "keyword"` |
| By extension | `es ext:pdf` |
| Multiple extensions | `es ext:ppt\|pptx` |
| Limit to directory | `es -path "C:\Users\Desktop" "keyword"` |
| Limit results | `es "keyword" -n 10` |
| Sort by date | `es "keyword" -s "date modified"` |
| Combine filters | `es -path "C:\Users" ext:docx "report" -n 5` |

## Important Syntax Rules

1. **Multiple extensions**: Use `ext:ppt|pptx` with pipe separator. Do NOT use `"*.ppt" "*.pptx"` as separate args — returns nothing.
2. **Always use `ext:` not `*.`**: `ext:pdf` is more reliable than `"*.pdf"`.
3. **Quoting**: Wrap search terms in quotes if they contain spaces.

## Usage Pattern

When user asks to find files:
1. Determine search scope (directory, extension, keyword)
2. Construct `es` command with appropriate filters
3. Run via Bash tool: `~/bin/es [options]`
4. Report results to user

## Examples

```
User: "找桌面上的PPT文件"
Command: ~/bin/es -path "C:\Users\Roder\Desktop" ext:ppt|pptx -n 20

User: "搜索电脑上所有关于合同的PDF"
Command: ~/bin/es "合同" ext:pdf -n 20

User: "找最近修改的Excel文件"
Command: ~/bin/es ext:xlsx|xls -s "date modified" -n 10
```
