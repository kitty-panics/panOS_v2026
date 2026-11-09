# 软件包管理

## pacman 与 pkg

底层即 pacman（Arch Testing 仓库），日常操作建议使用 `pkg` 封装：

```bash
pkg s firefox        # 搜索
pkg i firefox        # 安装
pkg u                # 全量更新
pkg c                # 清理缓存与孤儿包
```

## 玲珑（Linyaps）应用

除 pacman 外，系统集成如意玲珑应用商店，可临时安装各类国产软件：

```bash
ll-cli install <应用ID>     # 安装玲珑应用
```

或在应用商店 (网页版) 中点击安装需要的软件包。

## 占位空包（~/.local/.pkg/Fake）

为减小 ISO 体积，系统用 `arch-fake-pkg` 手工组装了一批**占位空包**
(版本 99999.99.99)，不含任何文件，仅提供 provides 关系）放在
`~/.local/.pkg/Fake`。

它们让 pacman 认为某些依赖已安装，从而裁掉大体积可选组件。

## 密钥环

Live 环境首次使用 pacman 前，`auto-pacman-key` 会在桌面就绪后自动执行：

```bash
pacman-key --init
pacman-key --populate
```

若手动操作遇签名错误，重新执行上述两条命令即可。

## AI 编程助手

集成腾讯 CodeBuddy Code，终端中输入 `codebuddy` 或 `cbc` 调用，详见 <https://www.codebuddy.cn>。
