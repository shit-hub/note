---

title: "Gvm"

weight: 3

bookFlatSection: false

bookToc: true

bookHidden: false

bookCollapseSection: false

bookComments: false

---

Shell 实现，故无法在 windows 上使用。

<!--more-->

GitHub 仓库：[gvm](https://github.com/moovweb/gvm)

## 安装

```bash
bash < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)
```

## 使用

```bash
gvm list # 列出当前安装的go版本
gvm listall # 列出可安装的go版本
gvm install go1.16 # 选择对应版本进行安装
gvm use go1.16 [--default] # 使用对应的go版本
```

> 注意：Go 1.5+从工具链中删除了 C 编译器，并将其替换为一个用 Go 编写的编译器。显然，如果你还没有一个正常的 Go 安装，这会造成一个引导问题。为了编译 Go 1.5+，请确保先安装 Go 1.4。

## 卸载原本的 go

{{< tabs "uniqueid" >}}
{{< tab "Linux" >}}

```bash
sudo rm -rf /usr/local/go
```

编辑 `/etc/profile` 删除相关的环境变量

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

## 卸载

```bash
gvm implode
```
