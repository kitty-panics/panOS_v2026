# 配置文件参考

## 目录速查（~/.config）

| 路径 | 用途 |
| --- | --- |
| `autostart/` | 开机自启项（自动缩放/壁纸/图标/密钥环、flameshot、clipman、复刻向导服务器） |
| `xfce4/xfconf/xfce-perchannel-xml/` | XFCE 全部设置（面板、快捷键、终端、窗口管理器…） |
| `fontconfig/fonts.conf` | 全局字体渲染（抗锯齿、hintslight、RGB 次像素、中文合成粗/斜体） |
| `fcitx5/` | 输入法框架与 Rime 配置 |
| `Kvantum/` | Qt 应用主题（KvLibadwaita，含明暗两套） |
| `qt5ct/` `qt6ct/` | Qt5/Qt6 外观（kvantum 风格 + HighContrast 图标） |
| `ranger/` | 文件管理器（multipane 视图、预览脚本） |
| `nvim/init.vim` | Neovim 配置 |
| `flameshot/flameshot.ini` | 截图工具（PNG、双击复制、X11 传统截图模式） |
| `mimeapps.list` | 文件类型默认打开方式 |
| `user-dirs.dirs` | XDG 用户目录（含自定义 `Projects`） |

## 字体渲染（fontconfig）

`~/.config/fontconfig/fonts.conf` 的关键策略：

- 全局抗锯齿 + `hintslight` 提示 + RGB 次像素排列 + LCD 过滤器
- 小于 12px 禁用嵌入位图，小于 10px 的非等宽字号提升到 10px
- 无原生粗体/斜体的字体启用合成粗体/合成斜体（对中文字体友好）
- 终端等宽字体：Source Code Pro；界面字体：Sans（随 DPI 缩放）

## 终端配色

xfce4-terminal 使用类 Doom-One 16 色调色板，背景 `#1f2022`、前景 `#a3a3a3`，85% 透明度。

## Neovim（~/.config/nvim/init.vim）

预置一份详尽的中文注释配置：

- 4 空格缩进（YAML/JSON 为 2 空格），空格替代 Tab
- 相对行号 + 当前行高亮，torte 主题，终端下背景透明
- `;` 进命令模式，`H`/`L` 跳行首/行尾，移动时光标保持居中
- `<Leader>w/q/x`（Leader 为空格）快速保存退出，`<C-hjkl>` 切换窗口
- 打开文件恢复上次光标位置，大文件自动关闭行号与语法高亮
- 自带 airline 风格状态栏（模式/文件/编码/位置/百分比）

## 桌面图标自动排列规则

`auto-fixed-icons` 读取 `~/Desktop/*.desktop` 文件名：

- 文件名中**第一个数字**决定所在列（0/1/2/3 → 四大分类列）
- 同列按文件名排序依次向下排
- 写回 `~/.config/xfce4/desktop/icons.screen0.yaml` 后重启 xfdesktop 生效

新增桌面图标时，按 `编号.名称.desktop` 命名即可自动进入网格。
