# Alacritty Configuration

**English** · [简体中文](README_zh.md)

Personal configuration for the [Alacritty](https://github.com/alacritty/alacritty) terminal emulator, used mainly under WSL2 (Ubuntu).

The main config pulls color schemes from `themes/` via `[general].import`, keeping color and feature configuration separate so themes are easy to switch.

## Configuration

Current `alacritty.toml` settings:

| Section | Key | Value | Description |
|---------|-----|-------|-------------|
| general | `import` | `themes/campbell.toml` | Imported color theme |
| window | `dimensions` | 180 cols × 52 lines | Initial window size |
| terminal | `osc52` | `CopyPaste` | Allow clipboard read/write via OSC 52 escape sequences |
| font | `size` | `12` | Font size |
| font | `normal` | `CaskaydiaCove NF` Regular | Monospace font (Nerd Font, includes icon glyphs) |
| font | `offset` | `y = 2` | Line-spacing tweak |
| selection | `save_to_clipboard` | `true` | Copy selected text to clipboard immediately |
| scrolling | `history` | `10000` | Scrollback buffer lines |

> To use the Windows WSL shell as the default in WSL, uncomment the `shell = "ubuntu.exe"` line under `[terminal]`.

## Theme: Campbell

`themes/campbell.toml` is the Windows 10 Terminal default color scheme (dark background `#0c0c0c`, foreground `#cccccc`). It enables `draw_bold_text_with_bright_colors`, so bold text is rendered using the bright color palette.

### Add / Switch Themes

1. Create a new color file under `themes/`, e.g. `themes/dracula.toml`;
2. Update the import in `alacritty.toml`:

   ```toml
   [general]
   import = [ "themes/dracula.toml" ]
   ```

See [alacritty-theme](https://github.com/alacritty/alacritty-theme) for ready-made themes.

## Dependencies

- **Alacritty** ≥ 0.13 (TOML config format)
- **CaskaydiaCove Nerd Font** — must be installed beforehand, otherwise icon glyphs won't render.
  Download: <https://github.com/ryanoasis/nerd-fonts/releases>

## Installation

Place (or symlink) this directory at Alacritty's config path:

- Linux / WSL: `~/.config/alacritty/`
- macOS: `~/.config/alacritty/` or `~/Library/Application Support/alacritty/`
- Windows: `%APPDATA%\alacritty\`

Changes take effect on save — Alacritty reloads automatically.
