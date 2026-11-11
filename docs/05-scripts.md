# 自研脚本 (~/.local/.bin)

系统的核心易用性来自这组脚本:

## 权限与运行

- **`run`** — 以 sudo 执行命令，通过 `run-passwd` askpass 免输密码 (live 用户)。
- **`run-passwd`** — sudo askpass 助手。

## 包管理

- **`pkg`** — pacman 封装:
 - `pkg i <名>` 安装；`pkg r <名>` 卸载；`pkg rr <名>` 连配置彻底卸载
 - `pkg u` 更新 (`-Fy` + `Syu`) ；`pkg fu` 强制刷新更新
 - `pkg s <词>` 搜索；`pkg l [N]` 列出最近安装的 N 个包
 - `pkg c` 清理缓存/孤儿包/.pacnew；`pkg cc` 清理循环依赖
- **`arch-fake-pkg <名> [provides...]`** — 手工组装空的 pacman 占位包 (版本 99999.99.99)，用于满足依赖而不实际安装文件。
- **`arch-debloated-pkgs.list`** — 对照 pkgforge-dev/archlinux-pkgs-debloated 的 mini/nano 减重包清单。

## 显示与外观

- **`xrandr-info`** — 解析当前显示器接口/分辨率/短边 (多个脚本的依赖)。
- **`light [0.1-1.0]`** — 用 xrandr gamma 调节屏幕亮度。
- **`auto-scaling-ui`** — 按分辨率自动缩放整套 UI (见「桌面环境」一章)。
- **`auto-wallpaper`** — 等待 xfdesktop 启动后为每个显示器应用预设壁纸。
- **`auto-fixed-icons`** — 按文件名编号自动排列桌面图标。
- **`auto-pacman-key`** — Live 环境下等待桌面就绪后初始化 pacman 密钥环。

## 浏览器相关

- **`chromium`** — Chromium 启动器，按分辨率自动设置 `--force-device-scale-factor` (1.25/1.15/1.0)，启用 GPU 光栅化；支持 `~/.config/chromium-flags.conf` 覆盖参数。
- **`chromium-player [URL]`** — 以应用模式打开网页/本地媒体 (微信、Office 等的载体)。
- **`man <命令>`** — 在 Chromium 中打开 Arch Linux Man 页搜索。

## 媒体与文件

- **`mime-open-player/-text/-linyaps`** — MIME 关联打开器: 媒体→播放器模式；文本→终端 nvim；`og://` 链接→玲珑 `ll-cli install`。
- **`wiremix`/`bluetui`/`htop`** — TUI 程序的终端启动封装。

## 服务器与部署

- **`tinyserver [地址] [端口] [目录]`** — Python http.server 封装 (默认 0.0.0.0:8080)。
- **`arch-installer-new`** — 在终端中运行 `archinstall` 全新安装 Arch Linux。

## 其它

- **`whcat <命令>`** — which + cat，查看某命令脚本内容。
- **`lsbin <包名>`** — 列出某软件包安装在 /usr/bin 的文件。
- **`reboot-bios`** — 重启进入固件设置 (UEFI)。
- **`reset-user-lock`** — 重置当前用户的登录失败锁定 (faillock)。
- **`cbc`/`codebuddy`** — CodeBuddy Code 命令行助手 (位于 `~/.local/.pkg/`)。

## 开机自启 (~/.config/autostart)

| 自启项 | 作用 |
| --- | --- |
| Auto: Scaling UI | 按分辨率自动缩放 UI |
| Auto: Fixed Desktop Icons | 自动排列桌面图标 |
| Auto: Wallpaper | 应用预设壁纸 |
| Auto: Pacman Keyring | Live 环境初始化 pacman 密钥环 |
| Flameshot | 截图工具常驻 |
| xfce4-clipman | 剪贴板管理 |
| Tiny Server (Fork panOS) | 本地复刻向导页面 |
