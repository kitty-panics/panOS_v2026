# 内置应用

桌面图标按文件名前缀编号分成四大类，`auto-fixed-icons` 脚本启动时按编号自动排列成网格：

| 前缀 | 分类 | 图标 |
| --- | --- | --- |
| `0000`–`0050` | 系统管理 | 此电脑、回收站、设置、网络、终端、音量、蓝牙 |
| `1000`–`1040` | 常用应用 | 应用商店、启动器、Chrome、媒体库、编辑器、截图、显示器 |
| `2000`–`2060` | Web 应用 | 邮箱、微信、文件传输助手、PhotoShop、文字、表格、演示 |
| `3000`–`3010` | 安装部署 | 全新安装、复刻 panOS |

图标文件位于 `~/.local/.icons/`，桌面入口均为标准 `.desktop` 文件（`X-AppStream-Ignore=True`）。

## 系统工具

| 应用 | 说明 |
| --- | --- |
| Thunar | 文件管理器，右键"在此处打开终端"会启动 ranger |
| Mousepad | 图形文本编辑器 |
| xfce4-settings-manager | 系统设置中心 |
| nm-connection-editor | 网络连接管理 |
| ARandR | 显示器屏幕排列 |
| flameshot | 截图工具（开机自启动，双击复制到剪贴板） |
| clipman | 剪贴板管理（历史 5 条文本 + 1 张图片，支持二维码） |

## TUI 工具（终端界面）

| 工具 | 用途 | 启动方式 |
| --- | --- | --- |
| `htop` | 进程/资源监视器 | `Ctrl+Shift+Esc` |
| `wiremix` | PipeWire 音量混音器（支持鼠标） | 桌面"音量"图标 |
| `bluetui` | 蓝牙设备管理 | 桌面"蓝牙"图标 |
| `ranger` | Vim 风格文件管理器（multipane 视图） | `Ctrl+Super+E` |
| `nvim` | 文本编辑器（见「配置文件参考」） | 双击文本文件自动以终端 nvim 打开 |
| `rofi` | 应用启动器（Arc 主题） | `Super+R` |

## Web 应用（chromium-player）

以下应用均以 Chromium **应用模式**运行（独立窗口、隐藏滚动条、独立 profile 存于 `/tmp/chromium-player`），观感与原生应用一致，可满足轻度使用和办公场景：

| 图标 | 实际内容 |
| --- | --- |
| 应用商店 | 如意玲珑应用商店 <https://store.linyaps.org.cn/> |
| 媒体库 | 本地图片/音乐/视频浏览（`file://$HOME`） |
| 邮箱 | 国内外主流邮箱导航页（本地 `~/.local/.pkg/E-Mail/index.html`） |
| 微信 | 微信网页版 <https://wx2.qq.com/> |
| 传输助手 | 微信文件传输助手网页版 |
| PhotoShop | Photopea 网页版 |
| 文字 / 表格 / 演示 | Microsoft Office 网页版（Word / Excel / PowerPoint） |

文件关联（MIME）：图片、音频、视频、PDF 双击后均以播放器模式打开；纯文本以终端 nvim 打开。

## AI 助手

集成腾讯 CodeBuddy Code：终端中输入 `codebuddy` 或 `cbc` 即可调用（见 <https://www.codebuddy.cn/>）。

## 维护工具

除桌面可见应用外，系统还包含引导、性能、磁盘、网络、日志等各类维护工具，配合
`archinstall` 安装器与复刻向导使用。完整预装软件清单见「软件包清单」一章。
