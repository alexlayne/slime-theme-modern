# Slime (Modern)

A dark workbench and syntax theme for [Visual Studio Code](https://code.visualstudio.com), updated to work with current versions of VS Code.

**Slime was designed and created by [Steve Lombardi](https://github.com/smlombardi).** This repository is a fork of the original [Slime theme for VS Code](https://github.com/smlombardi/theme-slime), which was itself a port of Steve's [Slime Atom theme](https://github.com/smlombardi/slime).

The original hasn't been updated since early 2020, and VS Code has added a lot of UI and highlighting features since then. This fork only brings the theme up to date: it keeps all of Steve's original colors and fills in what's missing, using the existing Slime palette. Alex Layne made the compatibility updates.

## What's changed from the original

**Workbench colors.** About 185 color keys for UI that didn't exist (or wasn't themed) in 2020, all drawn from the existing Slime palette:

- Command center, title bar, and menus
- Sticky scroll, inlay hints, and ghost text
- Bracket pair colorization
- Diff editor, peek view, and overview ruler
- Panel and terminal, tabs (active-tab top border, hover, pinned), and status bar items
- Dropdowns, checkboxes, input validation, buttons, and keybinding labels
- Notifications, quick input, breadcrumbs, settings editor, and git/testing decorations

**Semantic highlighting.** VS Code now uses semantic tokens for TypeScript and JavaScript, which can override TextMate rules. The theme enables semantic highlighting and pins the tokens that would otherwise lose their Slime color: parameters (italic), object-literal keys, type parameters, enum members, interfaces, and types.

**TSX/JSX support.** Many token rules only targeted `.js` or `.ts` scopes, so React files lost highlighting. Booleans, `null`/`undefined`, `this`, arrow functions, `console`, template literals, parameters, and primitive types now work across JS, TS, JSX, and TSX.

**Fixes.**

- The Markdown list-bullet rule used an Atom-style scope that never matched in VS Code.
- `terminal.ansiBrightBlack` was identical to `ansiBlack`, so it's now a lighter gray.

**Packaging.** Requires VS Code 1.80 or later, and the stale Marketplace metadata is removed.

## Install

This fork isn't published to the Marketplace. To install it, build the extension and install the `.vsix`:

```bash
git clone https://github.com/alexlayne/slime-theme-modern.git
cd slime-theme-modern
npx @vscode/vsce package --skip-license
code --install-extension slime-4.0.0.vsix
```

Then pick **Slime** from **Preferences: Color Theme**, or set it in `settings.json`:

```json
"workbench.colorTheme": "Slime"
```

The extension ID is still `smlombardi.slime`, so it replaces the original Marketplace version if you have it installed.

## Italic comments

Comments are italic by default. To turn this off, or to apply it under any other theme, override it in your user settings:

```json
"editor.tokenColorCustomizations": {
  "textMateRules": [
    {
      "scope": "comment, comment.block.html",
      "settings": { "fontStyle": "" }
    }
  ]
}
```

## Screenshots

These screenshots are from the original theme. Syntax colors are unchanged, but some newer UI elements are now themed as well.

### Workbench
![Workbench](screenshots/screenshot.png)

### HTML
![HTML](screenshots/html.png)

### SCSS
![SCSS](screenshots/scss.png)

### JS
![JS](screenshots/js.png)

### TypeScript
![TypeScript](screenshots/ts.png)

### PHP
![PHP](screenshots/php.png)

## Credits

- **Theme design and original VS Code port:** [Steve Lombardi](https://github.com/smlombardi), in [smlombardi/theme-slime](https://github.com/smlombardi/theme-slime)
- **Compatibility updates for modern VS Code:** [Alex Layne](https://github.com/alexlayne)

The upstream repository doesn't include a license, so this fork doesn't add one either. All rights to the original theme remain with Steve Lombardi.
