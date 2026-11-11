# 系统维护

## 日常操作速查

```bash
pkg u         # 日常更新 (Testing 仓库滚动)
pkg c         # 清理缓存、孤儿包、检查 .pacnew
htop         # 查看资源占用 (Ctrl+Shift+Esc)
light 0.7       # 降低屏幕亮度 (0.1–1.0)
reboot-bios      # 重启进 BIOS/UEFI 设置
reset-user-lock    # 解除登录失败锁定
```

## 远程管理

- 默认启用 SSH 服务，可用 `live/live` 或 `root/root` 密码直接连接:

 ```bash
 ssh live@<主机地址>
 ```

## 浏览器数据

- Web 应用数据在 `/tmp/chromium-player` 与 `/tmp/mime-open-player` (重启即清空)。

## 日志与排查

- 系统日志: `journalctl -b` (本次启动) 、`journalctl -xe` (最新错误)。
- 磁盘: `lsblk` 查看分区、`df -h` 查看占用。
- 网络: `nm-connection-editor` (GUI) 或 `ip a`。
- 登录失败锁定: 多次输错密码后可用 `reset-user-lock` 解锁。
