# panOS v2026

English | [简体中文]

[简体中文]: README.md

![panOS_v2026](images/panOS_v2026.png)

> This project is essentially production-ready. The ISO will only be updated from time to time to keep base components current.

## Features

- ~~Around 1GB — smaller than Arch's official TTY ArchISO.~~ (Lite ISO no longer published)
- Built from the [Testing repo], rolls and updates regularly.
- Boots in both BIOS and UEFI, plug and play.
- Ships with Xfce4 — clean and minimal, adapts to any screen resolution.
- Chinese fonts and input methods preconfigured — ready to go for Chinese users.
- Bundles all sorts of maintenance tools — boot, performance, disk, network, logs, and more.
- A hand-picked set of online apps, enough for light use and office work.
- VirtualBox + VMware guest additions built in — smoother in VMs.
- Comes with the [Linyaps App Store] for installing various domestic apps on the fly.
- Tencent [CodeBuddy Code] integration — type codebuddy / cbc in your terminal to launch it.
- Shortcuts kept close to Windows so it feels familiar.

[Testing repo]: https://wiki.archlinux.org/title/Official_repositories#Testing_repositories
[Linyaps App Store]: https://store.linyaps.org.cn/
[CodeBuddy Code]: https://www.codebuddy.cn/

## Usage

#### 1. Username is the password.

> SSH is on by default — you can connect with a password.

- User: `live`, password: `live`.
- User: `root`, password: `root`.

#### 2. Input method is `fcitx5 + rime`, with full Pinyin (Simplified Chinese) installed.

- `Ctrl + Space` to switch between Chinese and English.
- `Ctrl + ;` to open the clipboard.

#### 3. `~/.local/.bin` has some custom scripts.

#### 4. `~/ .local/.pkg/Fake` has some placeholder empty packages to keep the ISO small.

#### 5. Use `run` instead of `sudo` so you don't have to type a password.

## Download

- [Releases · kitty-panics/panOS_v2026]

[Releases · kitty-panics/panOS_v2026]: https://github.com/kitty-panics/panOS_v2026/releases

## Installation

- For a fresh Arch Linux install, click the "Fresh Install" desktop icon — it runs `archinstall` and walks you through it.
- To keep using panOS v2026 as a base, click the "Replicate panOS" desktop icon — a detailed doc pops up to walk you through it.

## v2027 Plans

- [ ] ~~Move the base to Debian Sid.~~
- [ ] Plugin support, so you can sideload more apps without growing the ISO.
- [X] More built-in maintenance tools, covering more scenarios.
- [ ] Full switch to Wayland.
