# 安装与复刻

镜像支持 **BIOS/UEFI 双模启动**，写入 U 盘后即插即用。桌面提供两条部署路径:

## 全新安装 (archinstall)

双击桌面"**全新安装**"图标，在终端中运行官方 `archinstall` 交互式安装器，得到一个干净的 Arch Linux。

## 复刻 panOS

要在 panOS 基础上继续使用，双击 "**复刻panOS**" 图标，会打开本地向导页面，大致流程:

### 1. 分区 (至少 ESP + ROOT)

```bash
parted -s --align optimal /dev/sda mklabel gpt
parted -s --align optimal /dev/sda mkpart ESP 0% 128MiB
parted -s --align optimal /dev/sda mkpart ROOT 128MiB 100%
mkfs.fat -F 32 -n "panOS-ESP" /dev/sda1
mkfs.ext4 -L "panOS-ROOT" /dev/sda2
```

### 2. 挂载并解压 live 根文件系统

```bash
mount /dev/sda2 /mnt
mkdir -p /mnt/boot/esp
mount /dev/sda1 /mnt/boot/esp
unsquashfs -f -d /mnt /run/archiso/copytoram/airootfs.sfs
```

### 3. 生成 fstab 与统一内核镜像 (UKI)

```bash
cp -a /mnt/etc/fstab.bak /mnt/etc/fstab
cp -a /mnt/usr/lib/modules/$(uname -r)/vmlinuz /mnt/boot/vmlinuz-linux-zen
arch-chroot /mnt mkinitcpio -P
```

### 4. 重启

```bash
umount -R /mnt
reboot
```

### 5. 补全缺失文件 (可选)

对于缺失的系统文件，可以通过下面命令补全:

```bash
pacman-key --init
pacman-key --populate
```

## 在虚拟机中使用

系统内置 VirtualBox 与 VMware 增强插件 (guest Additions)，
在虚拟机中开箱即用，共享文件夹、自适应分辨率等功能无需额外安装。
