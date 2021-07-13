---
title: "Libevent库"
weight: 1
bookFlatSection: false
bookToc: true
bookHidden: false
bookCollapseSection: false
bookComments: false
---

<!--more-->

Libevent 是一个用C语言编写的、轻量级的开源高性能事件通知库.
## 特点
- 事件驱动（ event-driven）高性能
- 轻量级，专注于网络
- 源代码相当精炼、易读
- 跨平台，支持 Windows、 Linux、 *BSD 和 Mac Os
- 支持多种 I/O 多路复用技术， epoll、 poll、 dev/poll、 select 和 kqueue 等
- 支持 I/O，定时器和信号等事件；注册事件优先级。

## 组成
- 事件管理包括各种IO（socket）、定时器、信号等事件，也是libevent应用最广的模块；
- 缓存管理是指evbuffer功能；
- DNS是libevent提供的一个异步DNS查询功能；
- HTTP是libevent的一个轻量级http实现，包括服务器和客户端
## 安装
- 手动安装
```
git clone https://github.com/libevent/libevent.git
cd libevent
./configure
make
make verify   # (optional)
sudo make install
```
- 自动安装
```bash
apt-cache search libevent
apt-get install libevent-dev
```