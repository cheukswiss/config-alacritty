# Alacritty 配置

**简体中文** · [English](README.md)

[Alacritty](https://github.com/alacritty/alacritty) 终端模拟器的个人配置，主要在 WSL2 (Ubuntu) 环境下使用。

主配置通过 `[general].import` 引入 `themes/` 下的配色文件，配色与功能配置分离，便于切换主题。

## 配置说明

`alacritty.toml` 当前设置：

| 分类 | 配置项 | 值 | 说明 |
|------|--------|----|------|
| general | `import` | `themes/campbell.toml` | 引入的配色主题 |
| window | `dimensions` | 180 列 × 52 行 | 启动窗口尺寸 |
| terminal | `osc52` | `CopyPaste` | 允许通过 OSC 52 转义序列读写系统剪贴板 |
| font | `size` | `12` | 字号 |
| font | `normal` | `CaskaydiaCove NF` Regular | 等宽字体（Nerd Font，含图标字形） |
| font | `offset` | `y = 2` | 行间距微调 |
| selection | `save_to_clipboard` | `true` | 选中文本即写入剪贴板 |
| scrolling | `history` | `10000` | 回滚缓冲行数 |

> 在 WSL 中若想用 Windows 的 WSL 作为默认 shell，可取消 `[terminal]` 中 `shell = "ubuntu.exe"` 一行的注释。

## 主题：Campbell

`themes/campbell.toml` 为 Windows 10 终端默认配色（深色背景 `#0c0c0c`，前景 `#cccccc`），启用了 `draw_bold_text_with_bright_colors`，粗体文本使用 bright 系列颜色绘制。

### 新增 / 切换主题

1. 在 `themes/` 下新建配色文件，例如 `themes/dracula.toml`；
2. 修改 `alacritty.toml` 的 import：

   ```toml
   [general]
   import = [ "themes/dracula.toml" ]
   ```

更多现成主题见 [alacritty-theme](https://github.com/alacritty/alacritty-theme)。

## 依赖

- **Alacritty** ≥ 0.13（TOML 配置格式）
- **CaskaydiaCove Nerd Font** — 需提前安装，否则图标字形无法显示。
  下载：<https://github.com/ryanoasis/nerd-fonts/releases>

## 安装

将本目录置于（或软链接到）Alacritty 的配置路径：

- Linux / WSL：`~/.config/alacritty/`
- macOS：`~/.config/alacritty/` 或 `~/Library/Application Support/alacritty/`
- Windows：`%APPDATA%\alacritty\`

修改配置后保存即可生效，Alacritty 会自动热重载。

