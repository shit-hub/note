---
title: "SS/V2ray搭建"
weight: 4
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: true
---

<!--more-->

# Shadowsock
## 安装
```
$ cd /usr/local/src 
$ wget --no-check-certificate -O shadowsocks.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh
$ chmod +x shadowsocks.sh 
$ systemctl stop firewalld && systemctl disable firewalld 
$ ./shadowsocks.sh 2>&1 | tee shadowsocks.log
```
## 配置shadowsock
```txt
Please enter password for shadowsocks-python
(Default password: teddysun.com):   // 配置登录密码
---------------------------
password = *******
---------------------------

Please enter a port for shadowsocks-python [1-65535]
(Default port: 16849):                      //配置服务端口
---------------------------
port = 16849
---------------------------

Please select stream cipher for shadowsocks-python:
1) aes-256-gcm
2) aes-192-gcm
3) aes-128-gcm
4) aes-256-ctr
5) aes-192-ctr
6) aes-128-ctr
7) aes-256-cfb
8) aes-192-cfb
9) aes-128-cfb
10) camellia-128-cfb
11) camellia-192-cfb
12) camellia-256-cfb
13) chacha20-ietf-poly1305
14) chacha20-ietf
15) chacha20
16) rc4-md5
Which cipher you'd select(Default: aes-256-gcm):        //选择加密协议
---------------------------
cipher = aes-256-cfb
---------------------------

Press any key to start...or Press Ctrl+C to cancel
```
## 记录shadowsock信息
```
Congratulations, Shadowsocks-python server install completed!
Your Server IP : *.*.*.*
Your Server Port : 16849 
Your Password : ***********
Your Encryption Method: aes-256-cfb 
```

## 服务使用
```
START: /etc/init.d/shadowsocks start 
STOP:  /etc/init.d/shadowsocks stop 
RESTART: /etc/init.d/shadowsocks restart 
STATUS: /etc/init.d/shadowsocks status 
CONFIG: /etc/shadowsocks.json 
UNINSTALL: /usr/local/src/shadowsocks.sh uninstall
```

## 使用软件连接shadowsock即可
WIN : [https://github.com/shadowsocks/shadowsocks-windows/releases](https://github.com/shadowsocks/shadowsocks-windows/releases)
Andriod ： 待添加

## 加速
安全起见，最好先把服务器进行备份，然后执行以下操作
```
$ wget "https://github.com/chiakge/Linux-NetSpeed/raw/master/tcp.sh" 
$ chmod +x tcp.sh 
$ ./tcp.sh
```
## 选择内核并重启
```
 TCP加速 一键安装管理脚本 [v1.3.2]
  -- 就是爱生活 | 94ish.me --
  
 0. 升级脚本
--------------------内核管理--------------------
 1. 安装 BBR/BBR魔改版内核
 2. 安装 BBRplus版内核 
 3. 安装 Lotserver(锐速)内核
--------------------加速管理--------------------
 4. 使用BBR加速
 5. 使用BBR魔改版加速
 6. 使用暴力BBR魔改版加速(不支持部分系统)
 7. 使用BBRplus版加速
 8. 使用Lotserver(锐速)加速
--------------------杂项管理--------------------
 9. 卸载全部加速
 10. 系统配置优化
 11. 退出脚本
-----------------------------------------------------

 当前状态: 已安装 BBR 加速内核 , BBR启动成功

 请输入数字 [0-11]:   2  <-- Enter the num of the kernel
```

# V2ray
```bash
bash < (curl -s -L https://git.io/v2ray.sh)
```

