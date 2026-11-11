# 输入法 (fcitx5 + Rime)

## 基本配置

- 输入法框架 **Fcitx5**，引擎 **Rime (中州韵) **，已安装全拼简体中文输入方案。
- 默认布局 `us`，输入法组: keyboard-us + rime。

## 快捷键

| 快捷键 | 功能 |
| --- | --- |
| `Ctrl + Space` | 中英文输入法切换 |
| `Ctrl + ;` | 打开剪贴板 (fcitx5 剪贴板) |

## 配置文件位置

| 路径 | 用途 |
| --- | --- |
| `~/.config/fcitx5/profile` | 输入法组 (keyboard-us + rime) |
| `~/.config/fcitx5/config` | 全局行为与热键 |
| `~/.config/fcitx5/conf/classicui.conf` | 候选窗外观 |
| `~/.config/fcitx5/conf/clipboard.conf` | 剪贴板行为 |

系统同时保留 ibus/fcitx 的 dbus 会话文件，可自行切换框架。
