# 软件包清单

> 适用于绝大多数维护场景需要用到的软件包清单。

## 引导 / 安装 / 时间

安装/修复引导器、管理 UEFI 启动项、安装 Arch、系统时间。

| 类别 | 包名 | 常用命令 | 作用 |
|------|------|----------|------|
| 引导器 / EFI | systemd     | bootctl | systemd-boot 管理 |
|              | grub        | grub-install,grub-mkconfig | 安装/配置 GRUB，支持 UEFI/BIOS |
|              | refind      | refind-install | 安装 rEFInd UEFI 引导管理器 |
|              | syslinux    | syslinux,extlinux | 传统轻量引导器，按需保留 |
|              | efibootmgr  | efibootmgr | 查看/增删 UEFI 启动项 |
|              | os-prober   | os-prober | 探测其他系统，供 GRUB 生成菜单 |
| 系统安装     | archinstall | archinstall | 交互式 Arch 安装向导 |
|              | arch-install-scripts | pacstrap,arch-chroot,genfstab | 手动安装 Arch 的核心脚本 |
| 时间同步     | chrony      | chronyc,systemctl | NTP 时间同步 |

## 硬件信息 / 电源 / 服务器管理

传感器、PCI/USB、DMI、CPU/内存拓扑、ACPI、IPMI 带外管理、TPM 检查。

| 类别 | 包名 | 常用命令 | 作用 |
|------|------|----------|------|
| 传感器      | lm_sensors | sensors,sensors-detect | 温度/电压/风扇传感器 |
| PCI 信息    | pciutils   | lspci,update-pciids | PCI 设备与驱动信息 |
| 硬件/块设备 | util-linux | lscpu,lsblk,blkid,dmesg,mount | CPU/块设备/挂载/内核日志基础工具 |
| DMI 信息    | dmidecode  | dmidecode | DMI/SMBIOS 硬件信息 |
| 硬件拓扑    | hwloc      | lstopo,hwloc-info | CPU/内存/NUMA 拓扑 |
| USB 信息    | usbutils   | lsusb | USB 设备与拓扑 |
| 硬件清单    | lshw       | lshw | 完整硬件清单 |
| 电源/ACPI   | acpi       | acpi | 电池、温度、电源状态 |
|             | acpid      | systemctl | 电源按钮/合盖等 ACPI 事件 |
| 服务器管理  | ipmitool   | ipmitool | IPMI/BMC 带外管理 |
| 安全/固件   | tpm2-tools | tpm2_getcap,tpm2_pcrread | TPM 2.0 状态与 PCR 检查 |

## 进程 / 性能 / 诊断

进程与 IO 监控、文件/端口占用、系统调用跟踪、历史性能统计、进程辅助操作。

| 类别 | 包名 | 常用命令 | 作用 |
|------|------|----------|------|
| 进程/系统状态 | procps-ng | ps,top,free,vmstat,pgrep,pkill | 进程、内存、系统状态查看 |
| 内核模块      | kmod      | lsmod,modprobe,modinfo,rmmod | 内核模块加载/卸载/查询 |
| 进程辅助      | psmisc    | killall,fuser,pstree | 按名杀进程、端口/文件占用、进程树 |
| 进程/IO 监控  | htop      | htop | 交互式进程与资源查看 |
|               | iotop     | iotop | 按进程查看磁盘 IO |
|               | lsof      | lsof | 查看进程打开的文件、端口 |
|               | strace    | strace | 跟踪系统调用，排障 |
| 性能统计      | sysstat   | sar,iostat,mpstat,pidstat | 历史/实时性能数据采集 |

## 磁盘 / 文件系统 / 数据救援

磁盘健康与设备信息、分区、文件系统创建/修复、LVM/RAID/多路径、分区表/文件恢复与安全擦除。

| 类别 | 包名 | 常用命令 | 作用 |
|------|------|----------|------|
| 文件系统      | e2fsprogs   | mkfs.ext4,e2fsck,resize2fs,tune2fs,dumpe2fs | ext2/3/4 创建、检查、调整 |
|               | dosfstools  | mkfs.fat,fsck.fat | FAT 创建与修复 |
|               | exfatprogs  | mkfs.exfat,fsck.exfat | exFAT 创建与修复 |
|               | xfsprogs    | mkfs.xfs,xfs_repair,xfs_growfs | XFS 创建、修复、扩容 |
|               | btrfs-progs | btrfs,btrfs check,btrfs scrub | Btrfs 子卷/检查/校验 |
|               | f2fs-tools  | mkfs.f2fs,fsck.f2fs | F2FS 创建与修复 |
|               | ntfsprogs   | ntfsfix,ntfsinfo,ntfsclone,ntfsresize | NTFS 修复、信息、克隆、调整 |
|               | squashfs-tools | mksquashfs,unsquashfs | 制作/解包 squashfs 镜像 |
| 加密卷        | cryptsetup  | cryptsetup | LUKS 加密卷管理 |
| 磁盘健康      | smartmontools | smartctl | SATA/SAS SMART 检测 |
|               | nvme-cli    | nvme   | NVMe 信息与健康日志 |
|               | hdparm      | hdparm | 硬盘参数查看与测速 |
|               | sg3_utils   | sg_scan,sg_inq | SCSI/SAS 设备查询与诊断 |
| 分区/分区表   | parted      | parted | 分区查看/调整，支持 GPT |
|               | gptfdisk    | gdisk,sgdisk | GPT 分区专用工具 |
|               | gpart       | gpart | 猜测/恢复损坏的分区表 |
| 分区/文件恢复 | testdisk    | testdisk,photorec | 分区表修复、误删文件恢复 |
| LVM/RAID      | lvm2        | pvscan,vgscan,lvscan,lvs | LVM 卷管理 |
|               | mdadm       | mdadm | 软 RAID 管理与组装 |
| 多路径        | multipath-tools | multipath,multipathd | 多路径 SAN 设备管理 |
| 数据救援/擦除 | ddrescue    | ddrescue | 坏盘/坏分区数据救援 |
|               | foremost    | foremost | 按文件签名恢复已删文件 |
|               | wipe        | wipe | 安全擦除文件/目录 |

## 网络 / 网络存储 / RPC / 串口

有线/无线连接、DNS/路由/抓包/流量诊断、iSCSI/CIFS/NFS/RPC 排查、串口 console 维护。

| 类别 | 包名 | 常用命令 | 作用 |
|------|------|----------|------|
| 无线         | wpa_supplicant | wpa_supplicant,wpa_cli | WPA/WPA2 无线连接 |
|              | iwd        | iwctl | 无线网络连接管理 |
| HTTP         | curl       | curl | HTTP/HTTPS 请求与下载 |
| 网络与连接   | iputils    | ping,tracepath,arping | 连通性/路径/ARP 测试 |
|              | iproute2   | ip,ss,tc,bridge | 地址/路由/端口/流量控制/网桥 |
|              | dhcpcd     | dhcpcd | DHCP 客户端 |
|              | inetutils  | telnet,ftp,hostname | 基础网络客户端工具 |
|              | net-tools  | ifconfig,route,netstat | 传统网络查看，建议逐步用 iproute2 |
|              | netcat     | nc | TCP/UDP 连接测试与监听 |
|              | socat      | socat | 多功能网络连接/转发 |
| DNS/路由诊断 | bind       | dig,nslookup | DNS 查询与诊断 |
|              | ldns       | drill | 轻量 DNS 查询 |
|              | whois      | whois | 查询域名/IP 注册与归属信息 |
|              | traceroute | traceroute | 路径追踪 |
|              | mtr        | mtr | 持续路径与丢包诊断 |
| 网卡         | ethtool    | ethtool | 网卡速率/驱动/统计 |
| 带宽测试     | iperf3     | iperf3 | 网络吞吐测试 |
| 流量监控     | iftop      | iftop | 按连接实时流量 |
|              | nethogs    | nethogs | 按进程实时流量 |
|              | nload      | nload | 实时网卡流量 |
|              | bmon       | bmon | 带宽监控 |
| 抓包         | tcpdump    | tcpdump | 抓包分析 |
| 网络存储/RPC | open-iscsi | iscsiadm | iSCSI 发现与登录 |
|              | open-isns  | isnsadm,systemctl | iSNS 发现服务 |
|              | cifs-utils | mount | 挂载 SMB/CIFS 共享 |
|              | nfs-utils  | showmount,mount | NFS 导出查看与挂载 |
|              | rpcbind    | rpcinfo | RPC/portmapper 查询 |
| 串口         | minicom    | minicom | 串口 console 维护 |
|              | picocom    | picocom | 轻量串口终端 |

## 日志

系统/内核日志查看、日志轮转。

| 类别 | 包名 | 常用命令 | 作用 |
|------|------|----------|------|
| 日志查看 | systemd    | journalctl | systemd journal 日志查看 |
|          | util-linux | dmesg | 内核环形缓冲区日志 |
| 日志轮转 | logrotate  | logrotate | 日志轮转 |

## 内存测试 / Windows 救援

内存故障测试、Windows 本地账户密码应急处理。

| 类别 | 包名 | 常用命令 | 作用 |
|------|------|----------|------|
| 内存测试     | memtest86+-iso | 从引导菜单启动 memtest86+ | 引导级严格内存测试 |
|              | memtester      | memtester | 运行中用户空间内存压力测试 |
| Windows 救援 | chntpw         | chntpw | 清除/修改 Windows 本地账户密码 |
