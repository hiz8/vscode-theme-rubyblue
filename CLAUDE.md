# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

VS Code color theme extension called "Ruby Blue" - a dark, high contrast theme based on the Ruby Blue Brackets Theme.

## Testing

Press F5 in VS Code to launch Extension Development Host, then activate the theme with `Ctrl+K Ctrl+T`.

Validate JSON syntax:
```bash
python3 -c "import json; json.load(open('themes/RubyBlue-color-theme.json'))"
```

## Theme File Structure

Main theme file: `themes/RubyBlue-color-theme.json`

- `colors`: UI color definitions (300+ tokens)
- `tokenColors`: Syntax highlighting scopes (52 entries)
- `semanticTokenColors`: Semantic token colors (26 entries)

## Core Color Palette

| Purpose | Color |
|---------|-------|
| Background | #112435 |
| Foreground | #f8f8f2 |
| Selection | #3e7087 |
| Keywords/Types | #82C6E0 |
| Variables/Tags | #7BD827 |
| Strings | #F08047 |
| Constants | #F4C20B |
| Functions/Classes | #A6E22E |
| Parameters | #FD971F |
| Comments | #999999 |

## Code Style

- 2 spaces indentation (no tabs)
- CRLF line endings
- UTF-8 encoding
- Trailing newline required
- Hex colors: 6 or 8 characters preferred (#RRGGBB or #RRGGBBAA)

## Key References

- [VS Code Theme Color Reference](https://code.visualstudio.com/api/references/theme-color)
- [TextMate Scope Naming](https://www.sublimetext.com/docs/scope_naming.html)
- Use "Developer: Inspect Editor Tokens and Scopes" command to find scope names
