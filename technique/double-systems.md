---
description: 安装windows和ubuntu双系统（含虚拟机）
---

# 安装双系统或虚拟机

方案有很多，以下简单列出三种。

## 方案一：虚拟机

直接安装相应软件即可。

### 优点

虚拟机可以使得运行Windows时同时运行Ubuntu，并且能够很方便的隔离或互通（共享文件、端口映射）；能够相当方便地删除和安装，避免因为分区表、BIOS、引导等问题造成的麻烦。通过选择虚拟磁盘文件的模式，可以动态占用物理磁盘空间。

### 缺点

吃资源，同时运行两个系统对硬件消耗较大。如果想要优良的体验，磁盘性能、CPU性能、内存大小都不能太差。

### 推荐

+ VMware Player （免费，基本可用）
+ VMware Work Station （付费，紫荆有破解版，可以使用快照等）
+ VirtualBox  (开源免费但有时候可能卡，Windows/MacOS/Linux均可用)
+ Parallel Desktop （付费，MacOS用）

## 方案二：物理双系统

**推荐使用GPT磁盘分区或者分硬盘安装（Windows和Ubuntu分别单独一个硬盘），MBR磁盘分区可能会带来不必要麻烦！**

步骤基本如下：

1. 在原先的系统中，划分出一块未分配的分区（多块硬盘则直接是一个空盘）
2. 刻录Ubuntu安装盘（建议较新的Ubuntu）
3. 调整计算机的BIOS使得计算机可以U盘启动安装盘
4. 安装过程省略（过程不建议安装更新，太慢），注意是GPT分区的话会识别已经存在的Windows并且提供“与Windows共存”的选项。此为傻瓜选项，可以直接勾上继续安装即可自动完成。
5. 默认会使用grub引导，不建议修改Windows启动项来引导Ubuntu，很容易引导崩掉。

### 优点

可以完整利用系统的硬件性能。

### 缺点

不能与Windows互通（最多可以读取Windows分区的文件），不注意的话引导容易出问题，占用确定的磁盘空间，需要提前规划磁盘空间。Linux下个别驱动可能存在问题。

### 推荐

没啥好推荐的，GPT分区+最新LTS的Ubuntu即可顺利安装。

## 方案三、Windows Subsystem for Linux（WSL）

Windows10的功能，需要手动开启。开启方法见(Windows Subsystem for Linux Installation Guide for Windows 10)[https://docs.microsoft.com/en-us/windows/wsl/install-win10]

### 优点

可以在运行Windows的基础上运行Ubuntu，并且文件、网络可以互通，占用资源小。近乎原生的Ubuntu server体验。

### 缺点

没有桌面，只有命令行。Ubuntu的功能基本完整但仍有极少不支持。

命令行不得不用Windows下的PowerShell或cmd，所以很丑。

### 推荐

桌面问题可以通过手动安装桌面环境，配置vnc通过Windows下的vnc viewer一类的软件将其作为远程桌面访问。由于桌面吃资源推荐使用一些如xfce4的轻量桌面。

命令行问题可以通过安装cmder或者其他一类Windows下的美化终端解决。

## 方案总结

方案 | 空间占用 | 硬件性能需求 | 系统互通性 | 可视桌面 | 风险 |安装难度
---|---|---|---|---|---|---
虚拟机 | 可变 | 高 | 好 | 有 | 几乎无 |无
物理双系统|固定，较大|普通|差|有|引导、驱动问题|有一定难度 
WSL|小|普通|好|无，可简易配置|容易误删文件|无