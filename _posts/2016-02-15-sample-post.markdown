---
layout: post
title: OS X El Capitan 制作U盘安装盘
date: 2016-02-15 15:32:24.000000000 +09:00
---

①下载安装程序：
从 App Store中下载完整的（Install OS X El Captain / 安装 OS X El Captain） 安装程序，该安装程序下载完后会存放在（应用程序 / Applications）文件夹中。

请注意，此时一定不要直接启动该程序安装 OS X El Captain，因为一旦安装完后该安装程序会被删除。至少，你应该先做完独立安装介质之后再启动该程序安装。

②准备独立安装盘介质：你需要一个容量至少大于 `8GB` 的移动存储设备，比如 U 盘、移动硬盘或 SD 卡，将其插入 Mac，并启动磁盘工具对该介质执行”抹掉”操作，抹掉前请备份好该介质中的重要数据。首先确定自己的U盘分区方案为GUID分区表（如果不是可以在分区里选择选项进行修改）盘符名请命名为 `Untitled` 格式`Mac OS Extended (Journaled)` / `Mac OS 扩展（日志式）`。

③进行安装盘制作:
方法一：（终端命令一键制作安装盘）
通过”终端”命令制作安装盘：打开 “终端”, 在命令行中执行下面的命令，当提示输入密码时请输入你的OS X管理员登陆密码。（注意终端内输入密码不会显示）

```shell
sudo /Applications/Install\ OS\ X\ El\ Capitan.app/Contents/Resources/createinstallmedia --volume /Volumes/Untitled --applicationpath /Applications/Install\ OS\ X\ El\ Capitan.app --nointeraction
```

直接复制代码，然后 `command+v` 粘贴到 “终端” 就可以了
