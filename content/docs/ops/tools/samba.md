---
title: "Samba"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: true
---

<!--more-->

# Samba
在嵌入式系统开发应用平台中，tftp、nfs和samba服务器是最常用的文件传输工具，tftp和nfs是在嵌入式Linux开发环境中经常使用的传输工具，samba则是Linux和Windows之间的文件传输工具。samba是模仿Windows网上邻居的SMB的通讯协议，将Linux操作系统“假装成”Windows操作系统，通过网上邻居的方式来进行文件传输的。

## Module
samba有两个主要的进程smbd和nmbd。smbd进程提供了文件和打印服务，而nmbd则提供了NetBIOS名称服务和浏览支持，帮助SMB客户定位服务器，处理所有基于UDP的协议。

- /etc/samba/smb.conf 
这是samba的主要配置文件，基本上仅有这个文件，而且这个配置文件本身的说明非常详细。主要的设置包括服务器全局设置，如工作组、NetBIOS名称和密码等级，以及共享目录的相关设置，如实际目录、共享资源名称和权限等两大部分。
- /etc/samba/lmhosts 
早期的 NetBIOS name 需额外设定，因此需要这个 lmhosts 的 NetBIOS name 对应的 IP 檔。 事实上它有点像是 /etc/hosts 的功能.只不过这个 lmhosts 对应的主机名是 NetBIOS name 
- /etc/sysconfig/samba 
提供启动 smbd, nmbd 时，你还想要加入的相关服务参数。
- /etc/samba/smbusers 
由于 Windows 与 Linux 在管理员与访客的账号名称不一致，例如： administrator (windows) 及 root(linux)， 为了对应这两者之间的账号关系，可使用这个档案来设定
- /var/lib/samba/private/{passdb.tdb,secrets.tdb} 
管理 Samba 的用户账号/密码时，会用到的数据库档案；
- /usr/share/doc/samba-<版本> 
这个目录包含了 SAMBA 的所有相关的技术手册

## Installation
#### Update soft source
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
```
#### Install samba server 
```
sudo apt-get install samba samba-common
```
#### Add user to samba
```
sudo smbpasswd -a casa
```

#### Config samba
```
vim /etc/samba/smb.conf
```
```
[home]
   path = /home/casa
   public = yes
   browseable = yes
   public = yes
   read only = no
   writable = yes
   #valid users = user
   create mask = 0777
   directory mask = 0777
   #force user = nobody
   #force group =nogroup
   available = yes
   security = share

```
#### Restart samba
```
service smbd restart
```
