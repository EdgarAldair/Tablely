# Tablely

<p align="center">
  <img src="https://github.com/user-attachments/assets/c6af23cd-7e64-4197-8268-cff2002e8956" width="400" alt="Tablely logo" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/973d0794-5a5a-446f-8c85-4cf54771d4a2" width="160%" alt="Tablely preview" />
</p>
<br>
<br>
<br>
A dark VS Code theme with floating glass panels, rounded corners, pill-shaped activity bar, and smooth transitions — built on an Ember Dark palette centered around warm orange-amber tones.

---

## Features

- Deep navy canvas (`#050710`) behind all floating panels
- Directional glass borders — brighter top/left, subtle bottom/right
- Rounded corners on all panels, notifications, command palette, and sidebars
- Pill-shaped activity bar with glass selection indicators
- Breadcrumbs and status bar that fade until hovered
- Tab close buttons that fade in on hover
- Smooth transitions on sidebar selections, scrollbars, and status bar
- Pill-shaped scrollbar with a subtle orange tint
- Minimap with unified background and orange-tinted viewport slider
- Icon glow effect with color matching (works best with **Seti Folder** icon theme)
- Ember Dark syntax: orange (`#d4683a`), amber (`#c8892a`), light coral (`#e8a070`), teal (`#6ab8c0`)

---

## Installation

Tablely has two parts: the color theme, and CSS customizations via **Custom UI Style** that create the floating glass panel effect.

### Step 1 — Install the theme

Clone the repo and copy the extension files:

```bash
git clone https://github.com/EdgarAldair/Tablely.git tablely
cd tablely
mkdir -p ~/.vscode/extensions/edgaraldair.tablely-0.1.0
cp package.json ~/.vscode/extensions/edgaraldair.tablely-0.1.0/
cp -r themes ~/.vscode/extensions/edgaraldair.tablely-0.1.0/
```

### Step 2 — Install Custom UI Style

The floating panels, rounded corners, glass borders, and animations all require the **Custom UI Style** extension.

1. Open Extensions (`Cmd+Shift+X` / `Ctrl+Shift+X`)
2. Search for `Custom UI Style` by **subframe7536**
3. Click Install

### Step 3 — Install the recommended icon theme

For the best icon glow effect, install **Seti Folder**:

1. Open Extensions (`Cmd+Shift+X`)
2. Search for `Seti Folder` by **l-igh-t**
3. Click Install
4. Activate it: Command Palette → `Preferences: File Icon Theme` → `Seti Folder`

### Step 4 — Install the UI font

Tablely uses **Bear Sans UI** for the sidebar, tabs, command center, and status bar. The font files are included in the `fonts/` folder.

- **macOS**: Open the `fonts/` folder, select all `.otf` files, double-click to open in Font Book
- **Windows**: Select all `.otf` files, right-click → Install

> Bear Sans UI must be installed for the UI to render correctly.

### Step 5 — Apply the settings

Merge the contents of `settings.json` from this repo into your VS Code user settings:

1. Open Command Palette (`Cmd+Shift+P`)
2. Search for `Preferences: Open User Settings (JSON)`
3. Copy and merge the contents of `settings.json` into your config

> **Important:** Do not replace your entire settings file — only merge the keys from this file. This preserves your existing configuration (fonts, keybindings, extensions, etc.).

### Step 6 — Enable Custom UI Style

1. Open Command Palette (`Cmd+Shift+P`)
2. Run `Custom UI Style: Enable`
3. VS Code will reload

> You may see a "corrupted installation" warning. This is expected — Custom UI Style injects CSS into VS Code. Click the gear icon and select **Don't Show Again**.

---

## Editor font & ligatures (optional)

The `settings.json` in this repo intentionally does **not** include `editor.fontFamily` or `editor.fontLigatures` — those are personal preferences and would override your existing setup.

If you want to match the setup this theme was designed with, add these to your **personal** `settings.json`:

```jsonc
// Recommended editor font with ligatures
"editor.fontFamily": "'FiraCode Nerd Font Mono', monospace",
"editor.fontSize": 13,
"editor.fontLigatures": true,

// Recommended terminal font (supports Nerd Font icons)
"terminal.integrated.fontFamily": "'FiraCode Nerd Font Mono'",
```

**FiraCode Nerd Font Mono** must be installed separately:
- Download from [nerdfonts.com](https://www.nerdfonts.com/font-downloads) → search for **FiraCode**
- Install the font files on your system
- Fully quit and restart VS Code (`Cmd+Q`, then reopen)

> Ligatures only activate after a full restart — `Developer: Reload Window` is not enough.

---

## Customization

All key visual properties are controlled by CSS variables in `settings.json`. Edit the variables under `.monaco-workbench` to adjust the look:

```jsonc
".monaco-workbench": {
    "--tablely-panel-radius": "20px",
    "--tablely-widget-radius": "12px",
    "--tablely-input-radius": "8px",
    "--tablely-item-radius": "3px",
    "--tablely-panel-gap": "6px",
    "--tablely-panel-top": "6px",
    "--tablely-bg-canvas": "#050710",
    "--tablely-bg-surface": "#0a0d11"
}
```

| Variable | Default | Applies to |
|---|---|---|
| `--tablely-bg-canvas` | `#050710` | Deep background behind all panels |
| `--tablely-bg-surface` | `#0a0d11` | Editor, sidebar, and panel backgrounds |
| `--tablely-panel-radius` | `20px` | Sidebar, editor, bottom terminal/panel |
| `--tablely-widget-radius` | `12px` | Notifications, command palette |
| `--tablely-input-radius` | `8px` | Search bars, buttons, tooltips |
| `--tablely-item-radius` | `3px` | List rows, tabs, panel headers |
| `--tablely-panel-gap` | `6px` | Horizontal spacing between panels |
| `--tablely-panel-top` | `6px` | Top margin of panels |

After editing any CSS variable, run `Custom UI Style: Reload` from the Command Palette to apply changes.

---

## Color palette

| Role | Hex | Used for |
|---|---|---|
| Canvas | `#050710` | Deepest background layer |
| Surface | `#0a0d11` | Editor and sidebar background |
| Panel | `#131a22` | Titlebar, status bar, dropdowns |
| Orange (hero) | `#d4683a` | Strings, activity bar, buttons, main accent |
| Light coral | `#e8a070` | Functions and entities |
| Amber | `#c8892a` | Types and support classes |
| Red-orange | `#c55e35` | Keywords |
| Teal | `#6ab8c0` | Constants and units |
| Cream | `#dbd6cc` | Main text |
| Mid-gray | `#7a8494` | Status bar, secondary elements |
| Comment | `#5a4f48` | Comments (italic) |

---

## Troubleshooting

**Panels don't look rounded / glass effect is missing**
→ Make sure Custom UI Style is installed and enabled (`Custom UI Style: Enable`)

**Activity bar is horizontal**
→ Remove or comment out `"workbench.activityBar.location": "top"` from your settings — the CSS is designed for the vertical side activity bar

**Ligatures are not showing**
→ Fully quit VS Code (`Cmd+Q`) and reopen — `Developer: Reload Window` is not sufficient for font changes

**"Corrupted installation" warning**
→ This is normal when Custom UI Style is active. Click the gear and select **Don't Show Again**

---

## License

MIT
