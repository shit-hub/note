---

title: Go Module 加速

weight: 4

bookFlatSection: false

bookToc: true

bookHidden: false

bookCollapseSection: false

bookComments: false

---

<!--more-->

## 代理源

### Goproxy 中国

中国最可靠的 Go 模块代理。

Goproxy 中国完全实现了 Go 的[模块代理协议](https://golang.org/cmd/go/#hdr-Module_proxy_protocol)。并且它是一个由中国备受信赖的云服务提供商[七牛云](https://www.qiniu.com)支持的非营利性项目。我们的目标是为中国和世界上其他地方的 Gopher 们提供一个免费的、可靠的、持续在线的且经过 CDN 加速的模块代理。请在 [status.goproxy.cn](https://status.goproxy.cn) 订阅我们的有关系统性能的实时和历史数据。

请注意，Goproxy 中国只专注于服务在 [https://goproxy.cn](https://goproxy.cn) 的 Web 应用本身的开发。如果你正在寻找一种极其简单的方法来搭建你自己的 Go 模块代理，那么你应该看一下 [Goproxy](https://github.com/goproxy/goproxy)，Goproxy 中国就是基于它开发的。

**代理地址：<https://goproxy.cn>**

### 阿里云 Go Module 代理仓库服务

go module 公共代理仓库，代理并缓存 go 模块。你可以利用该代理来避免 DNS 污染导致的模块拉取缓慢或失败的问题，加速你的构建

**代理地址：<https://mirrors.aliyun.com/goproxy/>**

## 用法

设置以下两个环境变量

```bash
GO111MODULE=on  # Go1.16之后默认开启，可以不设置
GOPROXY=https://goproxy.cn,direct
```

设置方法参考[环境变量](./环境变量)
