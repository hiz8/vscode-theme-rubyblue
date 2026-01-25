# CLAUDE.md - AI Assistant Guide for vscode-theme-rubyblue

This document provides comprehensive guidance for AI assistants working on the RubyBlue Theme VS Code extension.

## Project Overview

**Project Name:** RubyBlue Theme
**Type:** Visual Studio Code Color Theme Extension
**Description:** A dark, high contrast theme for Visual Studio Code
**Version:** 3.0.0
**License:** MIT
**Publisher:** hirofumii
**Repository:** https://github.com/hiz8/vscode-theme-rubyblue
**Minimum VS Code Version:** ^1.80.0

### Purpose

This is a VS Code extension that provides a single color theme called "Ruby Blue". It's based on the Ruby Blue Brackets Theme, which itself is an adaptation of the original RubyBlue theme by John Long. Version 3.0.0 brings the theme up to modern VS Code standards with comprehensive UI color tokens, semantic highlighting support, and adherence to current best practices.

## Repository Structure

```
vscode-theme-rubyblue/
├── .vscode/                         # VS Code workspace configuration
│   ├── extensions.json              # Recommended extensions
│   ├── launch.json                  # Launch configuration for testing
│   └── settings.json                # Workspace editor settings
├── themes/                          # Theme definition files
│   └── RubyBlue-color-theme.json   # Main theme file (modern JSON format)
├── .editorconfig                    # EditorConfig settings
├── .gitignore                       # Git ignore rules
├── CLAUDE.md                        # AI Assistant guidance (this file)
├── CONTRIBUTING.md                  # Contribution guidelines
├── LICENSE                          # MIT License
├── README.md                        # User-facing documentation
├── icon.png                         # Extension icon
└── package.json                     # Extension manifest
```

## Key Files and Their Purpose

### package.json

The extension manifest file that defines:

- Extension metadata (name, version, publisher, description)
- VS Code engine compatibility (`^1.80.0`)
- Theme contribution point
- Keywords for discoverability
- Links to repository, homepage, and issue tracker

**Important:** The theme is registered in the `contributes.themes` section:

```json
"contributes": {
  "themes": [{
    "label": "Ruby Blue",
    "uiTheme": "vs-dark",
    "path": "./themes/RubyBlue-color-theme.json"
  }]
}
```

### themes/RubyBlue-color-theme.json

The main theme definition file. Modern structure includes:

- `$schema`: VS Code color theme schema reference
- `name`: "Ruby Blue"
- `type`: "dark" - Indicates this is a dark theme
- `semanticHighlighting`: true - Enables semantic token support
- `colors`: Object with 200+ comprehensive UI color definitions
- `tokenColors`: Array with 52 token color scopes for syntax highlighting
- `semanticTokenColors`: Object defining colors for semantic tokens

**Key Color Categories:**

- **Editor Colors**: Background, foreground, selection, line highlight, cursor, whitespace, indent guides, line numbers, gutter
- **UI Components**: Activity Bar, Side Bar, Status Bar, Title Bar, Menu Bar, Tabs
- **Widgets**: Input fields, dropdowns, buttons, checkboxes, badges, notifications
- **Lists and Trees**: Selection states, hover states, focus states
- **Terminal**: Full ANSI color support (16 colors)
- **Git**: Decorations for modified, added, deleted, conflicting files
- **Diff Editor**: Inserted and removed text highlighting
- **Peek View**: Code preview window styling
- **Symbol Icons**: Colors for different symbol types in IntelliSense
- **Errors and Warnings**: Problem indicator colors

**Core Color Palette:**

- `editor.background`: Main editor background (#112435)
- `editor.foreground`: Main text color (#f8f8f2)
- `editor.selectionBackground`: Selection highlight (#3e7087)
- `editor.lineHighlightBackground`: Current line highlight (#16314a)
- `editorCursor.foreground`: Cursor color (#f8f8f2)
- `editorWhitespace.foreground`: Whitespace markers (#555555)
- `editorIndentGuide.activeBackground`: Active indent guide (#999999)

**Token Colors:** 52 different scopes covering comments, strings, keywords, functions, classes, variables, etc.

### .editorconfig

Defines coding style rules:

- Indent style: spaces (not tabs)
- Indent size: 2 spaces
- Line endings: CRLF
- Charset: UTF-8
- Trim trailing whitespace: yes
- Insert final newline: yes

### .vscode/settings.json

Workspace-specific VS Code settings that enforce:

- Tab size: 2
- Insert spaces: true
- Render whitespace: all
- Trim auto whitespace: true
- Trim final newlines: true
- Trim trailing whitespace: true

### .vscode/launch.json

Debug configuration for testing the extension:

- Name: "Launch Extension"
- Type: extensionHost
- Opens a new VS Code window with the extension loaded

## Code Conventions and Style Guide

### General Rules

1. **Indentation:** Use 2 spaces, never tabs
2. **Line Endings:** CRLF (Windows-style)
3. **Charset:** UTF-8
4. **Whitespace:** Trim trailing whitespace
5. **Final Newline:** Always include a newline at the end of files

### JSON Formatting

- Use 2-space indentation
- Follow standard JSON formatting rules
- Maintain consistency with existing structure

### Theme Development

When modifying `themes/RubyBlue.tmTheme.json`:

- Maintain alphabetical or logical grouping of color definitions
- Use hex color codes with 3, 6, or 8 characters (#RGB, #RRGGBB, or #RRGGBBAA)
- Test all changes in VS Code by launching the extension
- Document color purposes in commit messages
- Consider high contrast requirements for accessibility

### Color Palette

Key colors used in the theme:

- Background: #112435 (dark blue)
- Foreground: #f8f8f2 (off-white)
- Selection: #3e7087 (medium blue)
- Strings: #F08047 (orange)
- Numbers: #66d9ef (cyan)
- Constants: #F4C20B (yellow)
- Comments: #999999 (gray)

## Development Workflow

### Setting Up Development Environment

1. **Clone the repository:**

   ```bash
   git clone https://github.com/hiz8/vscode-theme-rubyblue.git
   cd vscode-theme-rubyblue
   ```

2. **Install recommended extensions:**
   - EditorConfig.EditorConfig
   - HookyQR.beautify
   - robertohuertasm.vscode-icons

3. **Open in VS Code:**
   ```bash
   code .
   ```

### Testing Theme Changes

1. **Launch Extension Host:**
   - Press F5 in VS Code, or
   - Go to Run and Debug view, select "Launch Extension", click Start
   - A new VS Code window opens with the extension loaded

2. **Activate the theme:**
   - In the Extension Development Host window:
   - Press Ctrl+K Ctrl+T (or Cmd+K Cmd+T on Mac)
   - Select "Ruby Blue" from the theme list

3. **Test with different file types:**
   - Create or open files in various languages (HTML, CSS, JavaScript, etc.)
   - Verify syntax highlighting appears correct
   - Check that colors have good contrast and readability

4. **Verify UI elements:**
   - Selection background
   - Current line highlight
   - Cursor visibility
   - Indent guides
   - Whitespace markers

### Making Theme Changes

1. **Edit the theme file:**

   ```bash
   # Open the main theme file
   code themes/RubyBlue.tmTheme.json
   ```

2. **Modify colors or scopes:**
   - For UI colors, edit the `colors` object
   - For syntax colors, edit entries in the `tokenColors` array
   - Each token color has a `name`, `scope`, and `settings`

3. **Reload the extension:**
   - In the Extension Development Host window
   - Press Ctrl+R (or Cmd+R on Mac) to reload
   - Or close and relaunch with F5

4. **Document your changes:**
   - Update version in `package.json` if releasing
   - Add entry to README.md under Release Notes
   - Write descriptive commit messages

## Git Workflow

### Branch Strategy

- Main branch: `main` (or check repository settings)
- Feature branches: Create descriptive branch names
- Always develop on feature branches for Claude Code sessions

### Commit Guidelines

1. **Write clear commit messages:**

   ```
   Update theme to fix indent guide being purple

   - Changed editorIndentGuide.activeBackground to #999999
   - Fixes issue where guides were using wrong color
   ```

2. **Commit frequently:**
   - Commit logical units of work
   - Don't bundle unrelated changes

3. **Before committing:**
   - Verify formatting follows .editorconfig rules
   - Test the theme still works
   - Check for syntax errors in JSON files

### Version Updates

When releasing a new version:

1. Update `version` field in `package.json`
2. Add release notes to README.md
3. Commit with message like "Bump version to X.Y.Z"
4. Create a git tag: `git tag vX.Y.Z`

## Common Tasks for AI Assistants

### Task: Add or Modify a Color

1. **For UI colors:**

   ```json
   // In themes/RubyBlue.tmTheme.json, under "colors"
   "editor.newFeature": "#hexcolor"
   ```

2. **For token colors:**

   ```json
   // In themes/RubyBlue.tmTheme.json, under "tokenColors"
   {
     "name": "Descriptive Name",
     "scope": "scope.name.here",
     "settings": {
       "foreground": "#hexcolor",
       "fontStyle": "bold italic" // optional
     }
   }
   ```

3. **Test the change** in the Extension Development Host

### Task: Fix Color Contrast Issue

1. Identify the problematic scope or UI element
2. Use a color contrast checker for accessibility
3. Adjust the color in the theme file
4. Test with actual code files
5. Verify readability in different lighting conditions

### Task: Add Support for New Language

Most languages work automatically through TextMate scopes. If specific styling is needed:

1. Research the language's TextMate grammar scopes
2. Add specific scope rules to `tokenColors` array
3. Test with sample files in that language
4. Document the addition in commit message

### Task: Update Documentation

1. **README.md:** User-facing changes, release notes, screenshots
2. **CONTRIBUTING.md:** Development guidelines, setup instructions
3. **CLAUDE.md:** This file - AI assistant guidance
4. **package.json:** Metadata, version numbers

### Task: Prepare for Release

1. Test thoroughly in Extension Development Host
2. Update version in `package.json` (follow semantic versioning)
3. Add release notes to README.md
4. Commit all changes
5. Create git tag
6. Push to repository
7. (Publisher only) Publish to VS Code Marketplace using `vsce`

## Testing Checklist

Before finalizing any theme changes:

- [ ] JSON syntax is valid (no trailing commas, proper quotes)
- [ ] All hex colors are valid (3, 6, or 8 characters)
- [ ] Theme loads without errors in Extension Development Host
- [ ] Test with HTML files
- [ ] Test with CSS files
- [ ] Test with JavaScript files
- [ ] Test with TypeScript files (if applicable)
- [ ] Test with Markdown files
- [ ] Selection is visible and high contrast
- [ ] Current line highlight is visible but not distracting
- [ ] Cursor is clearly visible
- [ ] Indent guides are visible (active guide is highlighted)
- [ ] Comments are distinguishable but not too bright
- [ ] Strings, numbers, and keywords have distinct colors
- [ ] No trailing whitespace added
- [ ] Final newline present in all edited files
- [ ] Follows 2-space indentation

## Important Notes for AI Assistants

### When Working on This Repository

1. **File Format:** The main theme file is JSON. Always validate JSON syntax before committing.

2. **No Build Process:** This is a simple theme extension with no compilation or build step. Changes to JSON files are immediately testable.

3. **Testing Required:** Always test theme changes in the Extension Development Host. Colors can look different than you expect.

4. **Version Management:** Don't bump version numbers unless explicitly requested or preparing for release.

5. **Scope Names:** When adding token colors, use proper TextMate scope names. Reference the TextMate manual or VS Code's scope inspector (Developer: Inspect Editor Tokens and Scopes).

6. **Modern Standards:** VS Code engine version is `^1.80.0`. The theme utilizes modern features like semantic highlighting and comprehensive color tokens.

7. **Color Consistency:** Maintain the overall color scheme aesthetic. This is a blue-themed dark theme with orange/cyan accents.

8. **Accessibility:** Maintain high contrast ratios for readability. This is a "high contrast" theme per the description.

### Common Pitfalls

1. **Trailing Commas:** JSON doesn't allow trailing commas - these will break the theme
2. **Invalid Hex Colors:** Must be 3, 6, or 8 characters (RGB or RGBA)
3. **Scope Typos:** Misspelled scopes won't apply colors
4. **CRLF Line Endings:** This project uses Windows-style line endings
5. **Tab Characters:** Always use spaces, never tabs
6. **Missing Final Newline:** All files must end with a newline

### Color Reference Resources

- VS Code Theme Color Reference: https://code.visualstudio.com/api/references/theme-color
- TextMate Scope Naming: https://www.sublimetext.com/docs/scope_naming.html
- VS Code Syntax Highlight Guide: https://code.visualstudio.com/api/language-extensions/syntax-highlight-guide

### When Uncertain

1. **Read existing theme structure** - Pattern matching is safe
2. **Test incrementally** - Make small changes and test each
3. **Check git history** - See how similar changes were made: `git log --oneline`
4. **Validate JSON** - Use a JSON validator or VS Code's built-in validation
5. **Ask the user** - When in doubt about color choices or feature additions

## Quick Reference Commands

```bash
# Launch extension for testing
# (In VS Code: Press F5 or use Run and Debug)

# Validate JSON syntax
cat themes/RubyBlue.tmTheme.json | jq . > /dev/null && echo "Valid JSON"

# Check for trailing whitespace
grep -n '[[:space:]]$' themes/RubyBlue.tmTheme.json

# View git history
git log --oneline --graph

# View recent changes to theme
git log -p themes/RubyBlue.tmTheme.json

# Check current version
cat package.json | jq -r .version
```

## Project Goals and Philosophy

1. **High Contrast:** Maintain clear visual distinction between elements
2. **Dark Theme:** Preserve the dark background aesthetic
3. **RubyBlue Heritage:** Stay true to the Ruby Blue Brackets Theme
4. **Simplicity:** Keep the theme straightforward without excessive customization options
5. **Accessibility:** Ensure colors are readable and distinguishable

## Extension Publication

This section is primarily for the repository maintainer, but AI assistants should be aware:

1. Extension is published using `vsce` (Visual Studio Code Extension Manager)
2. Published to the VS Code Marketplace under publisher "hirofumii"
3. Extension name: "rubyblue-theme"
4. Display name: "RubyBlue Theme"

## Recent Changes (v3.0.0)

- **Major refactoring to modern VS Code theme standards**
- Updated minimum VS Code version to ^1.80.0
- Renamed theme file to RubyBlue-color-theme.json (follows modern naming convention)
- Added 200+ comprehensive UI color tokens
- Added semantic highlighting support
- Enhanced terminal, git decorations, and diff editor support
- Removed legacy theme files
- Updated workspace configuration to modern standards

---

**Last Updated:** 2025-11-17
**Document Version:** 2.0.0

This document should be updated whenever significant changes are made to the project structure, workflow, or conventions.
