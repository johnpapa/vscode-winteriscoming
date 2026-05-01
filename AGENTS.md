# Winter is Coming Theme — Agent Guide

A **VS Code color theme extension** providing dark and light themes with vibrant syntax highlighting. This is a theme-only extension — no runtime code, no build step, no tests.

## Repository Structure

```
vscode-winteriscoming/
├── themes/                          # Theme JSON files (the product)
│   ├── WinterIsComing-dark-blue-color-theme.json
│   ├── WinterIsComing-dark-blue-color-no-italics-theme.json
│   ├── WinterIsComing-dark-color-theme.json
│   ├── WinterIsComing-dark-color-no-italics-theme.json
│   ├── WinterIsComing-light-color-theme.json
│   └── WinterIsComing-light-color-no-italics-theme.json
├── images/                          # Screenshots and icon
│   └── winteriscoming-icon.png
├── .github/
│   ├── copilot-instructions.md      # AI contributor conventions
│   ├── dependabot.yml               # Dependency update automation
│   ├── ISSUE_TEMPLATE/              # Bug report and feature request forms
│   ├── PULL_REQUEST_TEMPLATE.md     # PR checklist
│   └── workflows/                   # CI (vsce package validation)
├── package.json                     # Extension manifest — defines themes, metadata, publisher
├── CHANGELOG.md                     # Version history (Keep a Changelog format)
├── CONTRIBUTING.md                  # Contribution guidelines
├── README.md                        # Overview, screenshots, installation, recommended settings
├── LICENSE.md                       # MIT
└── AGENTS.md                        # This file
```

## Tech Stack

- **Extension type:** VS Code color theme (no runtime code)
- **Theme format:** JSON color theme files following the [VS Code theme color reference](https://code.visualstudio.com/api/references/theme-color)
- **Manifest:** `package.json` — defines all theme contributions via `contributes.themes`
- **Packaging:** `vsce` (Visual Studio Code Extension manager) via `npx vsce package`
- **Publisher:** `johnpapa` on the VS Code Marketplace

## Theme Variants

| Theme | UI Theme | Italics | File |
|-------|----------|---------|------|
| Winter is Coming (Dark Blue) | `vs-dark` | Yes | `WinterIsComing-dark-blue-color-theme.json` |
| Winter is Coming (Dark Blue - No Italics) | `vs-dark` | No | `WinterIsComing-dark-blue-color-no-italics-theme.json` |
| Winter is Coming (Dark Black) | `vs-dark` | Yes | `WinterIsComing-dark-color-theme.json` |
| Winter is Coming (Dark Black - No Italics) | `vs-dark` | No | `WinterIsComing-dark-color-no-italics-theme.json` |
| Winter is Coming (Light) | `vs` | Yes | `WinterIsComing-light-color-theme.json` |
| Winter is Coming (Light - No Italics) | `vs` | No | `WinterIsComing-light-color-no-italics-theme.json` |

## Build & Run

There is no build step. The extension ships JSON theme files that VS Code reads directly.

```bash
# Package the extension into a .vsix file
npx vsce package

# List files that will be included in the package
npx vsce ls

# Publish to the VS Code Marketplace (requires publisher credentials)
npx vsce publish
```

**To test locally:** Press `F5` in VS Code to open an Extension Development Host, then select the theme from File > Preferences > Color Theme.

## Testing

There is no automated test suite — this is a theme-only extension with no runtime code.

**Manual validation:**
1. Open the repo in VS Code and press `F5` to launch the Extension Development Host
2. Switch between all 6 theme variants
3. Open files in various languages (HTML, JS, TS, CSS/SCSS, JSON, Markdown) and verify syntax colors
4. Check contrast for UI elements (sidebar, command palette, tabs, status bar, git decorations)

## Key Patterns and Conventions

- **Italics variants** — each base theme has a "No Italics" counterpart. The no-italics version removes `"fontStyle": "italic"` from all token rules. When modifying a theme color, apply the same change to both the italics and no-italics variants.
- **Theme naming** — files follow the pattern `WinterIsComing-{variant}-color-{suffix}-theme.json` where variant is `dark-blue`, `dark`, or `light`, and suffix is empty or `no-italics`.
- **Color consistency** — dark themes share accent colors (`#219fd5` blue, `#C792EA` purple, `#f7ecb5` yellow). Light themes use darker counterparts. Keep accent colors consistent across variants.
- **`package.json` is the product spec** — the `contributes.themes` array registers every theme. Each entry must have a correct `label`, `uiTheme` (`vs-dark` or `vs`), and `path` pointing to the theme JSON file.

## Adding a New Theme Variant

1. Copy the closest existing theme JSON file and rename it following the naming pattern
2. Modify colors in the new file
3. Register the new theme in `package.json` under `contributes.themes` with the correct `label`, `uiTheme`, and `path`
4. If the new theme should have a "No Italics" variant, duplicate the file and remove all `"fontStyle": "italic"` entries
5. Add a screenshot to `images/` showing the new theme
6. Update `README.md` with a new section showing the screenshot
7. Add a `CHANGELOG.md` entry
8. Bump `version` in `package.json`
9. Run `npx vsce package` to verify the extension packages correctly

## Documentation

This project does not have a docs site — documentation is in `README.md`. The README covers installation, screenshots of each theme variant, and recommended VS Code settings.

## Common Pitfalls

- **Forgetting the no-italics variant** — every color change to a base theme must also be applied to its no-italics counterpart. These files are not auto-generated.
- **Mismatched `package.json` paths** — if you rename a theme file, you must update the `path` in `contributes.themes` or the theme won't load.
- **Version bump** — `package.json` `version` must be bumped before publishing; `vsce publish` will fail if the version already exists on the Marketplace.
- **Screenshots** — update the `images/` directory when theme colors change significantly, so the README accurately represents the current look.
