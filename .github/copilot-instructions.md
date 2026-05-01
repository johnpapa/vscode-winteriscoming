# Copilot Instructions — Winter is Coming Theme

## Project Type

This is a **VS Code color theme extension** containing only JSON theme files and a `package.json` manifest. There is no source code to build, no test framework, and no runtime dependencies.

**Do not** generate build commands, test commands, package installs, or CI/CD pipelines for this repo.

## Theme Conventions

### Color Format

- Always use hex format: `#RRGGBB` or `#RRGGBBAA` (with alpha)
- Never use named colors (`red`, `blue`) — VS Code does not support them in themes
- Use lowercase hex digits for consistency: `#011627`, not `#011627` (already lowercase in this repo)

### Color Palette

The core palette for the Dark Blue theme:

| Role | Color | Usage |
|---|---|---|
| Background | `#011627` | Editor, sidebar, activity bar |
| Foreground | `#d6deeb` | Default text |
| Accent blue | `#82AAFF` | Keywords, operators |
| Accent cyan | `#7fdbca` | Strings, regex |
| Accent purple | `#C792EA` | Storage types, modifiers |
| Accent green | `#addb67` | Functions, methods |
| Accent orange | `#F78C6C` | Numbers, constants |
| Accent red | `#EF5350` | Errors, invalid tokens |
| Accent teal | `#5ABEB0` | Headings, section names |

### Contrast Guidelines

- Maintain sufficient contrast between foreground text and background colors
- Dark themes: light text on dark backgrounds (minimum 4.5:1 ratio for body text per WCAG AA)
- Light theme: dark text on light backgrounds
- Test readability with the VS Code built-in color picker or a contrast checker tool

### Font Styles

- Each base theme (Dark Blue, Dark Black, Light) has a "No Italics" counterpart
- The italics variant uses `"fontStyle": "italic"` on scopes like keywords, storage types, and comments
- The no-italics variant is identical but with all `"fontStyle": "italic"` entries removed
- When adding a new tokenColor rule with `fontStyle: "italic"`, also update the corresponding no-italics file to omit that style

### Naming Conventions

- Theme files: `WinterIsComing-<variant>-color-theme.json` (with optional `-no-italics` suffix)
- Theme labels in `package.json`: `"Winter is Coming (<Variant Name>)"` — capitalize each word, use parentheses
- No-italics labels: `"Winter is Coming (<Variant Name> - No Italics)"`

### tokenColors

- Group related scopes in a single rule when they share the same settings
- Use specific TextMate scopes — avoid overly broad scopes like `"source"` or `"text"`
- Order rules logically: general → language-specific → markup → special cases
- The first entry (no scope) sets the default foreground for the theme

### Workbench Colors (`colors` object)

- Use the VS Code [Theme Color Reference](https://code.visualstudio.com/api/references/theme-color) for key names
- Group related entries (all `editor.*` together, all `activityBar.*` together)
- When using alpha transparency, append two hex digits to the color: `#219fd544`

## Maintenance Matrix

| When this changes... | Also update... |
|---|---|
| Theme JSON file added/removed | `package.json` → `contributes.themes` (add/remove matching entry) |
| Theme JSON renamed | `package.json` → `contributes.themes` → `path` field |
| New theme variant added | `package.json`, `README.md` (screenshots section), `CHANGELOG.md` |
| Italics variant changed | Corresponding no-italics variant (mirror all changes except `fontStyle`) |
| Color palette changed in dark-blue | Consider applying same change to dark-black variant for consistency |
| `package.json` version bumped | `CHANGELOG.md` (add new version entry) |
| Screenshots updated | `README.md` (verify image paths) |
| New `uiTheme` type used | Verify VS Code engine version in `package.json` → `engines.vscode` supports it |

## File Editing Guidelines

- **Never overwrite an entire theme file** — theme JSON files are large (17–18 KB each). Make surgical edits to specific `colors` keys or `tokenColors` entries
- **Validate JSON** — theme files must be valid JSON. Use a JSON linter or `python3 -m json.tool < file.json` to verify
- **Test visually** — press `F5` in VS Code to launch the Extension Development Host and preview theme changes
