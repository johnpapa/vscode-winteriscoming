# Winter is Coming theme Changelog

<a name="1.4.3"></a>

## 1.4.3 (2020-05-09)

- Updated images in the README

<a name="1.4.1"></a>

## 1.4.1 (2020-03-15)

- Light theme changes
  - Updated the light theme to sync better with the dark and dark blue theme changes.
  - Added light theme with "no italics"
  - Changed `"gitDecoration.modifiedResourceForeground": "#1857a4"` as git changes were not detectable before. Fixes [#37](https://github.com/johnpapa/vscode-winteriscoming/issues/37)

<a name="1.3.1"></a>

## 1.3.1 (2020-03-13)

- Changed `"list.focusBackground": "#03648a"` as the contrast had changed due to VS Code changes. This applies to all 4 dark themes.

<a name="1.3.0"></a>

## 1.3.0 (2019-07-29)

- Add new version of the dark black theme with "no italics"

<a name="1.2.0"></a>

## 1.2.0 (2019-07-11)

- Modified the highlight colors for the dark themes

```json
    "editor.hoverHighlightBackground": "#0c4994",
    "editor.lineHighlightBackground": "#0c499477",
    "editor.selectionBackground": "#103362",
    "editor.selectionHighlightBackground": "#103362",
    "editor.findMatchHighlightBackground": "#103362",
    "editor.rangeHighlightBackground": "#103362",
    "editor.wordHighlightBackground": "#103362",
    "editor.wordHighlightStrongBackground": "#103362",
```

<a name="1.1.1"></a>

## 1.1.1 (2019-05-30)

- Added `"tab.activeBorderTop": "#219fd5",`
- Re-instated the dark black theme. Copied the dark blue theme to dark black and modified the editor background and selection bar colors. This may not be exact as much has been updated.
- Removed all remaining italics from the "no italics" version of the dark blue theme

<a name="1.0.0"></a>

## 1.0.0 (2019-04-27)

- Removed dark theme, as it was not well supported
- Added dark blue theme with no italics
- Refactored dark blue themes to add more contrast to JSON and javascript/typescript

<a name="0.9.0"></a>

## 0.9.0 (2019-03-11)

- Made both dark themes have a more readable warning messages
  - "inputValidation.warningBackground": "#f7ecb5",
  - "inputValidation.warningBorder": "#f7ecb5",
  - "inputValidation.warningForeground": "#000000",

<a name="0.8.9"></a>

## 0.8.9 (2019-03-01)

- Made both dark themes have a more subtle titlebar
  - "titleBar.activeBackground": "#112233",
  - "titleBar.inactiveBackground": "#000a11",

<a name="0.8.0"></a>

## 0.8.0 (2018-10-05)

- Dark blue theme
  - adjusted cursor color to contrast
  - `editorCursor.foreground`: `#219fd5`
  - adjusted the border colors to contrast, to make it easier to find splitters and borders
  - `activityBar.border`: `#219fd544`
  - `editorGroup.border`: `#219fd544`
  - `notificationToast.border`: `#219fd544`
  - `pickerGroup.border`: `#219fd544`
  - `sideBar.border`: `#219fd544`

<a name="0.7.2"></a>

## 0.7.2 (2018-09-29)

- Dark blue theme
  - adjusted the titleBar and border for the dark blue theme to make it have more contrast
  - `titleBar.activeBackground`: `#03648a`
  - `titleBar.border`: `#303030`

<a name="0.7.1"></a>

## 0.7.1 (2018-05-30)

- Changed `list.focusBackground` to `#0e293f` to keep the contrast in lists
  - e.g. open the command palette, use the down arrow and the backgroudn selection should be obvious
  - this color was transparent and made it difficult to see the selection
- minor change to make widget drop shadow's a light blue

<a name="0.7.0"></a>

## 0.7.0 (2018-05-25)

- 3 variations of Winter is Coming
  - Dark
  - Dark Blue
  - Light
- Created Winter is Coming (Dark Blue)
  - Variation of Winter is Coming but with a dark blue background
  - Inspired by the blue background of the Night Owl theme, by the awesome Sarah Drasner

<a name="0.6.2"></a>

## 0.6.2 (2018-05-21)

- Changes, as per user feedback
  - comments are now a shade of gray so they are not so pronounced as the green was
  - keyword operators are no longer italicized
  - entity.type.name is now a shade of purple, instead of teal (feedback was about the teal not matching)
  - variables reset to light blue (feedback wanted this reverted)
  - updated the readme images, fonts, and settings
  - more changes may come

<a name="0.6.1"></a>

## 0.6.1 (2018-05-20)

- Changes
  - Made several changes to increase color contrast

<a name="0.5.4"></a>

## 0.5.4 (2018-05-04)

- Changes
  - Updated indent lines based on new feature in VS Code
  - Dark theme
    - "editorIndentGuide.activeBackground": "#C792EA"
  - Light theme
    - "editorIndentGuide.activeBackground": "#2f86d2",
    - "editorIndentGuide.background": "#eff2ef"

<a name="0.5.3"></a>

## 0.5.3 (2018-03-20)

- Changes
  - Dark theme
    - constants are `#A170C6`
    - punctuation are `#ffffff`

<a name="0.5.2"></a>

## 0.5.2 (2018-03-17)

- Changes
  - Made dark theme's select background's more of a contrast
    - `"editor.selectionBackground": "#40537d",`
    - `"editor.selectionHighlightBackground": "#4f4f4f",`

<a name="0.5.1"></a>

## 0.5.1 (2018-03-06)

- [Bug fix](https://github.com/johnpapa/vscode-winteriscoming/pull/10) - thanks to [Kris](https://github.com/kriscoleman) for the PR

<a name="0.5.0"></a>

## 0.5.0 (2018-03-03)

- Changes
  - Variable from #96d5f9 to #b2d4fa to contrast with keywords
  - Minor shadings of light colors
  - Changed file name of theme to `WinterIsComing-dark-color-theme.json` in source code

<a name="0.4.7"></a>

## 0.4.7 (2017-11-20)

- Changes

  - debug bar border now matches debug status bar
  - dark theme
    - markdown bold #57cdff
    - markdown italic #C792EA
    - markdown raw string (inline code) #f7ecb5
    - markdown fenced code title #f7ecb5
  - light theme
    - markdown bold #4e76b5
    - markdown italic #C792EA
    - markdown raw string (inline code) #0460b1
    - markdown fenced code title #0460b1
    - `untrackedResourceForeground` is now clearer shade of green
    - `comment` is now clearer shade of green
    - `keyword` is now clearer shade of purple
    - `variable` is now clearer shade of blue

- These changes only apply to `.custom-vscodestyles.css`
  - italicized file tab font
  - default monaco `letter-spacing: .5px`
  - monaco panel title bar `letter-spacing: 1px;`
  - vs code's window title `color: #fafafa; letter-spacing: 1px; font-weight: 200;`

<a name="0.4.5"></a>

## 0.4.5 (2017-11-18)

- Changes

  - Comments are now gray
  - Removed the `editor.lineHighlightBorder` as it was hiding the cursor in some cases
  - Lightened `lineHighlightBackground` for light theme
  - Updated description

- These changes only apply to `.custom-vscodestyles.css`

  - to only affect dark theme where appropriate
  - make titlebar font yellow
  - yellow top and bottom border on debug bar

- Fixes
  - Fixed JSON string color for light them
  - Updated to the new name for `gitDecoration.modifiedResourceForeground`
  - Updated to the new name for `gitDecoration.untrackedResourceForeground`
  - Removed obsolete styles

<a name="0.4.0"></a>

## 0.4.0 (2017-11-16)

- Updated JSON file colors to blue and light yellow (for dark theme)
- Updated various constants to be #ec9cd2 (for dark theme)
- Italicized the comments and made them green (for dark theme)
- Matched light theme where applicable
- Added recommended settings to the README.md

<a name="0.3.2"></a>

## 0.3.2 (2017-11-08)

- Updated light color theme for HTML and CSS, based on Vue.js usage

<a name="0.3.1"></a>

## 0.3.1 (2017-10-31)

- Updated light color theme for `this`

<a name="0.3.0"></a>

## 0.3.0 (2017-10-26)

- Renamed theme to "Winter is Coming (dark)"
- Added a first draft of a light theme

<a name="0.2.1"></a>

## 0.2.1 (2017-10-23)

- sidebar list selection is same blue as theme
- added light green accents to git untracked badge

<a name="0.2.0"></a>

## 0.2.0 (2017-10-22)

- activity bar icons are blue
- line numbers are blue
- debugbar is lighter gray/black for contrast
- statusbar is same shade of blue as the theme
- debug statusbar is same shade of red/pink as the theme
- minor contrast adjustments
- peekview and find all references view now have better contrast
- peekview and find all references view has distinct border

<a name="0.1.4"></a>

## 0.1.4 (2017-10-20)

- Centered icon and reversed background
- Removed italics from most code
- Set function variables to soft purple/red
- Set `git.color.modified` to be blue

<a name="0.0.3"></a>

## 0.0.3 (2017-10-19)

- Set `git.color.modified` to be orange
- Set `git.color.untracked` to be green

<a name="0.0.2"></a>

## 0.0.2 (2017-10-18)

- Created Winter is Coming theme
