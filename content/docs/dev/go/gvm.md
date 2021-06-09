---
title: "使用Gvm更换go版本"
weight: 6
bookFlatSection: false
bookToc: true
bookHidden: false
bookCollapseSection: false
bookComments: false
---

<!--more-->

Source Code Location: [gvm](https://github.com/moovweb/gvm)

## Install
```bash
bash < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)
```

## Usage
```bash
gvm list # 列出当前安装的go版本
gvm listall # 列出可安装的go版本
gvm install go1.16 # 选择对应版本进行安装
gvm use go1.16 [--default] # 使用对应的go版本
```
> Note: Go 1.5+ removed the C compilers from the toolchain and replaced them with one written in Go. Obviously, this creates a bootstrapping problem if you don't already have a working Go install. In order to compile Go 1.5+, make sure Go 1.4 is installed first.

## Uninstall origin go verison
{{< tabs "uniqueid" >}}
{{< tab "Linux" >}}
```bash
sudo rm -rf /usr/local/go
```
Then edit `/etc/profile` to delete the following content:
```diff
- export PATH=$PATH:/usr/local/go/bin
```
{{< /tab >}}
{{< tab "MacOS" >}}
```bash
sudo rm -rf /etc/paths.d/go
```
{{< /tab >}}
{{< /tabs >}}

## Uninstall
```bash
gvm implode
```