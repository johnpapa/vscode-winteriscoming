# AI Agent Guide — Winter is Coming Theme

This is a **VS Code color theme extension** — it contains no runtime code, no build step, and no tests. The deliverables are JSON theme files that VS Code loads directly.

## Repository Structure

```
vscode-winteriscoming/
├── themes/                          # All theme JSON files
│   ├── WinterIsComing-dark-blue-color-theme.json
│   ├── WinterIsComing-dark-blue-color-no-italics-theme.json
│   ├── WinterIsComing-dark-color-theme.json
│   ├── WinterIsComing-dark-color-no-italics-theme.json
│   ├── WinterIsComing-light-color-theme.json
│   └── WinterIsComing-light-color-no-italics-theme.json
├── images/                          # Screenshots for README and marketplace
├── package.json                     # Extension manifest (theme registrations)
├── CHANGELOG.md                     # Version history
├── CONTRIBUTING.md                  # Contribution guidelines
├── README.md                        # Marketplace description and usage
├── LICENSE.md                       # MIT license
└── .github/
    └── copilot-instructions.md      # AI coding conventions
```

## Theme Variants

| Label | UI Theme | File | Description |
|---|---|---|---|
| Winter is Coming (Dark Blue) | `vs-dark` | `WinterIsComing-dark-blue-color-theme.json` | Dark theme with deep blue background (`#011627`) |
| Winter is Coming (Dark Blue - No Italics) | `vs-dark` | `WinterIsComing-dark-blue-color-no-italics-theme.json` | Same as Dark Blue without italic font styles |
| Winter is Coming (Dark Black) | `vs-dark` | `WinterIsComing-dark-color-theme.json` | Dark theme with black background |
| Winter is Coming (Dark Black - No Italics) | `vs-dark` | `WinterIsComing-dark-color-no-italics-theme.json` | Same as Dark Black without italic font styles |
| Winter is Coming (Light) | `vs` | `WinterIsComing-light-color-theme.json` | Light theme for presentations and bright environments |
| Winter is Coming (Light - No Italics) | `vs` | `WinterIsComing-light-color-no-italics-theme.json` | Same as Light without italic font styles |

Each base theme (Dark Blue, Dark Black, Light) has a "No Italics" variant. The no-italics version is identical except `fontStyle: "italic"` entries are removed from `tokenColors`.

## Theme JSON Format

Each theme file is a JSON object with these top-level keys:

```json
{
  "name": "Winter Is Coming",
  "type": "dark",
  "tokenColors": [ ... ],
  "colors": { ... }
}
```

| Key | Purpose |
|---|---|
| `name` | Display name (used internally by VS Code) |
| `type` | `"dark"` or `"light"` — tells VS Code the base theme type |
| `tokenColors` | Array of TextMate scope rules for syntax highlighting (foreground color, font style) |
| `colors` | Object mapping VS Code workbench color keys to hex values (activity bar, editor, sidebar, etc.) |

### tokenColors entries

```json
{
  "scope": ["keyword.control", "storage.type"],
  "settings": {
    "foreground": "#C792EA",
    "fontStyle": "italic"
  }
}
```

### colors entries

```json
{
  "activityBar.background": "#011627",
  "editor.background": "#011627",
  "editor.foreground": "#d6deeb"
}
```

See the [VS Code Theme Color Reference](https://code.visualstudio.com/api/references/theme-color) for all available color keys.

## How to Add a New Theme Variant

1. **Copy an existing theme file** — pick the closest base variant and copy it to `themes/` with a descriptive filename following the pattern `WinterIsComing-<variant>-color-theme.json`

2. **Edit the JSON** — modify `name`, `type`, `colors`, and `tokenColors` as needed

3. **Register in `package.json`** — add an entry to `contributes.themes`:
   ```json
   {
     "label": "Winter is Coming (<Variant Name>)",
     "uiTheme": "vs-dark",
     "path": "./themes/WinterIsComing-<variant>-color-theme.json"
   }
   ```
   Use `"vs-dark"` for dark themes, `"vs"` for light themes, or `"hc-black"` / `"hc-light"` for high contrast.

4. **Create a no-italics variant** (optional) — copy the new theme file, append `-no-italics` to the filename, remove all `"fontStyle": "italic"` entries, and register it in `package.json`

5. **Add screenshots** — capture representative screenshots and place them in `images/`

6. **Update README.md** — add a section showing the new variant's screenshots

7. **Update CHANGELOG.md** — document the new variant

8. **Bump version** — increment the `version` field in `package.json`

## Packaging and Publishing

```bash
# List files that will be included
npx vsce ls

# Package as .vsix
npx vsce package

# Publish to marketplace
npx vsce publish
```

## Common Pitfalls

- **Keep `package.json` and theme files in sync** — every theme JSON in `themes/` must have a matching entry in `contributes.themes`, and vice versa
- **Use valid hex colors** — VS Code requires `#RRGGBB` or `#RRGGBBAA` format; named colors are not supported
- **Don't add build or test infrastructure** — this is a theme-only extension with no code to compile or test
- **Test in VS Code** — press `F5` to open an Extension Development Host, then select the theme from File > Preferences > Color Theme to preview changes live
