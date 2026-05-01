# Copilot Instructions — Winter is Coming Theme

## Project Type

This is a **VS Code color theme extension**. There is no runtime code, no build step, and no test framework. The deliverables are JSON theme files and the `package.json` manifest.

## Theme Editing Conventions

### Color Values

- Use hex color codes in lowercase: `#219fd5`, not `#219FD5`
- Include alpha channel only when transparency is intentional: `#219fd544`
- Keep accent colors consistent across dark variants (`#219fd5` blue, `#C792EA` purple, `#f7ecb5` yellow)

### Token Colors

- Use VS Code's `tokenColors` array with `scope` (string or array) and `settings` (`foreground`, `fontStyle`)
- Use TextMate scope names — reference the [VS Code syntax highlighting guide](https://code.visualstudio.com/api/language-extensions/syntax-highlight-guide)
- When adding a new token rule, add it to **all 6 theme files** (or at minimum to both the italics and no-italics variants of the affected base theme)

### Workbench Colors

- Use the [VS Code theme color reference](https://code.visualstudio.com/api/references/theme-color) for valid property names
- Test contrast for accessibility — ensure text is readable against backgrounds

### Italics vs No-Italics

- The "No Italics" variants must have zero `"fontStyle": "italic"` entries
- When modifying a token in a base theme, apply the same color change to the no-italics variant but **do not** add `"fontStyle": "italic"`

## File Conventions

### JSON

- Use 2-space indentation (consistent with VS Code defaults)
- Theme files do not have a JSON schema reference — they follow the VS Code color theme format implicitly

### package.json

- `contributes.themes` must list every theme file with correct `label`, `uiTheme`, and `path`
- Bump `version` on every release
- Do not add runtime dependencies — this extension has none

### Images

- Screenshots go in `images/` as PNG files
- Use descriptive names: `dark-blue-ts.png`, `light-js.png`
- Keep image dimensions consistent for README display

## Maintenance Matrix

| When this changes... | Also update... |
|---|---|
| Theme colors in a base theme | Apply the same change to its "No Italics" variant |
| New theme variant added | `package.json` (`contributes.themes`), `README.md` (new section + screenshot), `CHANGELOG.md` |
| Theme file renamed or removed | `package.json` (`contributes.themes` path), `.vscodeignore` if applicable |
| `package.json` version bumped | `CHANGELOG.md` (new entry) |
| Screenshots updated | `README.md` (verify image references) |
| Extension icon changed | `package.json` (`icon` field), `images/winteriscoming-icon.png` |
