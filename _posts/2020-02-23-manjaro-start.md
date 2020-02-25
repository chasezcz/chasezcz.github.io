---
layout: post
title: Manjaro 安装教程
categories: [Linux]
description: 详细描述 Manjaro 的安装过程。
keywords: Manjaro install, Manjaro 安装
---

# 1. 选择版本以及下载镜像

## 选择桌面版本

在 Manjaro 的官网中，给出了最常用的，也是稳定的三种桌面版本：
- GNOME 版：

    长得和Ubuntu类似，性能稳定，样子平庸，交互较为简单。

- KDE 版 **（推荐）** ：

    最为炫酷  ~~(可装B)~~ ，同时要求性能较高，同时交互方式丰富，插件也很多。

- XFCE 版：

    最为轻便，但是很丑。。。

一般来说，对性能没有太大要求就上 KDE，喜欢简单交互就 XFCE 版，至于 Gnome 嘛，大部分都是从 Ubuntu 来的，谁不想换换口味呢？

**KDE 最棒，yeah！**

## 获取下载链接

国内的话，看区域网络状况，有时官网，呃，网络很差，下面列出一些常见的下载点，都可以使用：

- 官网下载：[https://manjaro.org/download](https://manjaro.org/download/)
- 清华镜像下载：[https://mirrors.tuna.tsinghua.edu.cn/osdn/storage/g/m/ma/manjaro](https://mirrors.tuna.tsinghua.edu.cn/osdn/storage/g/m/ma/manjaro/)

# 2. 刻录镜像到U盘

## Windows 用户

下载 [Rufus](http://rufus.akeo.ie) 工具进行操作

![这就是Rufus](/images/blog/2020-02-23-manjaro-start/rufus_en.png)

选项如下：

- `Partition Scheme (磁盘类型)`：如实填写，我的是 `UEFI`
- `File System`　以及 `Cluster size`：一般不需要修改

这时候点 `Start`，会提示 `ISO` 还是 `DD`，选择 `DD`

## Linux 用户

对于 linux 用户，因为发行版本差异，图形工具可能不统一，但是 shell 命令是一致的，所以采用 DD 命令来进行刻录。

1. 查到U盘的dev路径

    `sudo fdisk -l`

    之后如图

    ![dd效果图](/images/blog/2020-02-23-manjaro-start/dd.png)

    `/dev/sdc` 就是我的 4G U盘的 dev 路径。这个路径自己记下。

1. 使用 dd 命令

    `sudo dd bs=4M if=/path/to/manjaro.iso of=/dev/sdX status=progress oflag=sync`

    其中 `/path/to/manjaro.iso` 指的是你的 manjaro 安装镜像的绝对地址，`/dev/sdX` 指的是步骤 `1.` 中 dev 路径。

    之后，耐心等待 100% 即可。


# 3. 重启，进入 USB Live 环境

就是开机的时候狂按某一个键进入 USB 启动就好了。

# 4. Live 中的操作

## 设置源

打开终端，运行

`sudo pacman-mirrors -c China -m rank`

选取中国节点，之后强制更新所有源信息

`sudo pacman -Syy`

>更换源的操作为了防止出现卡在 93% `Misc postinstall configurations` 的错误。

## 分区

![live环境的安装](/images/blog/2020-02-23-manjaro-start/live.png)

这里选择 `擦除磁盘`来安装，如果自定义分区安装（双系统），可以使用

| 分区 | 大小 |
| :--: | :--: |
|  `swap`    |   `2G`   |
|   `/`   |   `剩余的空间`   |

> 注意：`/boot/efi` 请指定到原系统的 `efi` 分区，否则会无法引导。


## 安装


![](/images/blog/2020-02-23-manjaro-start/5minutes-later.png)

### 重启，enjoy Manjaro!
