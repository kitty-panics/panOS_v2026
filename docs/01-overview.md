# 系统概览

panOS v2026 是一个以 **简洁、轻量、开箱即用** 为目标的 Linux 发行版。

它基于 Arch Linux Testing 仓库构建，采用 XFCE 4 桌面环境与 X11 图形栈，运行
Linux-zen 内核。系统大量使用 TUI（终端界面）程序替代重型 GUI 工具，并以 Chromium
应用模式承载网页应用，在极小的体积内提供完整的桌面体验。

- 主页与下载：<https://github.com/kitty-panics/panOS_v2026/releases>
- 问题反馈：<https://github.com/kitty-panics/panOS_v2026/issues>
- 通用文档 (Arch Wiki)：<https://wiki.archlinux.org/>

## 基本信息

| 项目 | 内容 |
| --- | --- |
| 基础 | Arch Linux Testing 仓库（archiso 构建，live 环境根分区为 `airootfs`） |
| 版本 | panOS v2026（BUILD_ID=v2026） |
| 内核 | Linux-zen（preempt dynamic，面向桌面低延迟优化） |
| 桌面 | XFCE 4（X11 会话） |
| Shell | zsh |
| 启动 | BIOS / UEFI 双模启动，即插即用 |
| 主题 | GTK：Adwaita；Qt：Kvantum (KvLibadwaita)；图标：HighContrast |
| 品牌色 | `#1793D1`（RGB 23,147,209） |
| 虚拟机 | 内置 VirtualBox 与 VMware 增强插件，虚拟机中使用更顺手 |

## 账户与远程访问

**用户名即是密码**：

| 用户 | 密码 | 说明 |
| --- | --- | --- |
| `live` | `live` | 默认桌面用户 |
| `root` | `root` | 管理员账户 |

- 默认启用 **SSH 服务**，可通过密码直接远程连接。
- 桌面环境下用 `run` 命令代替 `sudo` 可免于输入密码（见「自研脚本」一章）。

## 设计理念

- **轻量优先**：用 TUI 程序（wiremix、bluetui、htop、ranger）替代重型 GUI；配合占位空包（`~/.local/.pkg/Fake`）减小 ISO 体积。
- **Web 即应用**：微信、Office、Photopea 等以 Chromium 应用模式（`chromium-player`）承载，不安装原生客户端。
- **自动化**：开机自检脚本自动完成 UI 缩放、桌面图标排列、壁纸应用、密钥环初始化。
- **贴近 Windows**：常用快捷键尽量贴近 Windows 习惯（Super 键组合），上手零成本。
- **可复刻**：整个系统可被"复刻"（克隆）到新磁盘，详见「安装与复刻」一章。
