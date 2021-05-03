---
title: "Go mod--依赖管理器"
weight: 2
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: true
---

<!--more-->

Environment: Ubuntu + Go 1.13
## Open Go module 
Add forrowing environment variable:
- 1.11 or 1.12
```bash
export GO111MODULE=on
export GOPROXY=https://goproxy.io
```
- 1.13 and later
```bash
go env -w GO111MODULE=on
go env -w GOPROXY=https://goproxy.cn,https://goproxy.io,direct
```
> Run that command after delete the origin environment variable.
## Usage: `go get`
使用go module之后，go get 拉取依赖的方式就发生了变化
下载项目依赖
```bash
go get ./...
```
拉取最新的版本(优先择取 tag)
```bash
go get golang.org/x/text@latest
```
拉取 master 分支的最新 commit
```bash
go get golang.org/x/text@master
```
拉取 tag 为 v0.3.2 的 commit
```bash
go get golang.org/x/text@v0.3.2
```
拉取 hash 为 342b231 的 commit，最终会被转换为 v0.3.2：
```bash
go get golang.org/x/text@342b2e
```
指定版本拉取，拉取v3版本
```bash
go get github.com/smartwalle/alipay/v3
```
更新
```bash
go get -u
```
## Usage: `go mod`
初始化一个moudle，模块名为你项目名
```bash
go mod init <module name>
```
下载modules到本地cache
目前所有模块版本数据均缓存在`$GOPATH/pkg/mod`和`$GOPATH/pkg/sum`下
```bash
go mod download
```
编辑go.mod文件 选项有-json、-require和-exclude，可以使用帮助go help mod edit
```bash
go mod edit
```
以文本模式打印模块需求图
```bash
go mod graph
```
删除错误或者不使用的modules
```bash
go mod tidy
```
生成vendor目录
```bash
go mod vendor
```
验证依赖是否正确
```bash
go mod verify
```
查找依赖
```bash
go mod why
```
## Advance usage
更新到最新版本
```bash
go get github.com/gogf/gf@version
```
> 如果没有指明 version 的情况下，则默认先下载打了 tag 的 release 版本，比如 v0.4.5 或者 v1.2.3；如果没有 release 版本，则下载最新的 pre release 版本，比如 v0.0.1-pre1。如果还没有则下载最新的 commit

更新到某个分支最新的代码
```bash
go get github.com/gogf/gf@master
```
更新到最新的修订版（只改bug的版本）
```bash
go get -u=patch github.com/gogf/gf
```
替代只能翻墙下载的库
```bash
go mod edit -replace=golang.org/x/crypto@v0.0.0=github.com/golang/crypto@latest
go mod edit -replace=golang.org/x/sys@v0.0.0=github.com/golang/sys@latest
```
清理moudle 缓存
```bash
go clean -modcache
```
查看可下载版本
```bash
go list -m -versions github.com/gogf/gf
```
