---
layout: wiki
title: Linux/Unix
categories: Linux
description: 常用命令和用法。
keywords: Linux
---

# 实用命令

## optirun

`optirun steam`

就是使用独显运行 `steam`

# 常用安装

## Shadowsocks/ShadowsocksR/bbr

### 方法一：

```
git clone -b master https://github.com/flyzy2005/ss-fly
cd ss-fly
./ss-fly -i %password% %port%
./ss-fly -bbr
```

### 方法二：

```
wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
chmod +x shadowsocks-all.sh
./shadowsocks-all.sh
wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh
chmod +x bbr.sh
./bbr.sh
```

建议选择 `shadowsocks-libev`
