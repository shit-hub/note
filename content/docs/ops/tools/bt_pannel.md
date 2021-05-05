---
title: "宝塔面板"
weight: 3
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: true
---

<!--more-->

#### 适用环境
- 虚拟主机
- 本地环境
- 云服务器

#### 特性
- 一键配置服务器环境（LAMP/LNMP）
- 一键安全重启
- 一键创建管理网站、ftp、数据库
- 一键配置（定期备份、数据导入、伪静态、301、SSL、子目录、反向代理、切换PHP版本）
- 一键安装常用PHP扩展(fileinfo、intl、opcache、imap、memcache、apc、redis、ioncube、imagick)
- 数据库一键导入导出
- 系统监控（CPU、内存、磁盘IO、网络IO）
- 防火墙端口放行SSH开启与关闭及SSH端口更改禁PING开启或关闭方便高效的文件管理器（上传、下载、压缩、解压、查看、编辑等等）计划任务（定期备份、日志切割、shell脚本）软件管理（一键安装、卸载、版本切换）

#### 安装
- centos：
```sh
yum install -y wget && wget -O install.sh http://download.bt.cn/install/install_6.0.sh && sh install.sh
```
- ubuntu/deepin:
```sh
wget -O install.sh http://download.bt.cn/install/install-ubuntu_6.0.sh && sudo bash install.sh
```
- Debian:
```sh
wget -O install.sh http://download.bt.cn/install/install-ubuntu_6.0.sh && bash install.sh
```
- Fedora:
```sh
wget -O install.sh http://download.bt.cn/install/install_6.0.sh && bash install.sh
```

#### 登录
安装完成后会显示以下一些信息：
```yml
Bt-Panel: http://A.B.C.D:8888/********
username: ******
password: ******
```
使用浏览器方位`Bt-Panel`后面的地址，然后根据提供的用户名和密码进行登录即可
> A.B.C.D是你设备的IP地址，初始登录需要时候后面的八位随机字符
> username和password也是随机生成的，可以登录后进行修改

#### 安装环境
登录后默认会提示安装LAMP或者LNMP，按需选择，等待完成即可
> LAMP : Linux + Apache + Mysql + PHP
> LNMP : Linux + Nginx + Mysql + PHP

#### 使用
一般在页面进行操作，不过也提供终端命令操作，详情请参考：
[https://www.bt.cn/btcode.html](https://www.bt.cn/btcode.html)