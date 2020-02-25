---
layout: post
title: Manjaro 安装双显卡驱动
categories: [Linux]
description: 再也不用记命令了
keywords: Linux, ubuntu, manjaro, 双显卡, Nvidia
---

# Manjaro 双显卡

## 1. 安装依赖

`sudo pacman -S virtualgl lib32-virtualgl lib32-primus primus`

## 2. 安装驱动

在图形化界面，硬件配置中，选择 `video-hybrid-intel-nvidia-440xx-prime` 打勾安装，之后把 `video-linux` 卸载掉。
![界面图](/images/blog/2020-02-25-manjaro-video/manjaro-double-VGA.png)

## 3. 配置

```
sudo systemctl enable bumblebeed
sudo gpasswd -a $USER bumblebee
reboot
```

## 4. 测试

`glxgears` 测试集成显卡的 FPS 数值。

`optirun glxgears` 测试独显的FPS。

![测试结果](/images/blog/2020-02-25-manjaro-video/test-result.png)

通过结果可以很明显的看出不同。

## 5. 使用

当遇到想要使用独显运行的程序，只需要在命令行前面加上 `optirun` 即可。
