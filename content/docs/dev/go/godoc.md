---
title: "Go doc--文档管理器"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: true
---

## 作用
打印与由Package相关参数（package，const，func，type，var，method或struct字段）标识的项目相关的文档注释，然后单行总结“ 项目（包的包级别声明，类型的方法等）。

## 使用方法
```bash
go doc [-u] [-c] [package|[package.]symbol[.methodOrField]]
```
| Option | Description |
| :-- | -- |
| -all | 显示所有文档 |
| -c | 匹配程序实体时，大小写敏感 |
| -cmd | 将命令（main包）视为常规程序包 | 
| -src | 显示完整源代码 |
| -u | 显示未导出的程序实体 |

## 编写文档规则
1. 注释: `// xxx`
2. 段落：行首字母大写
3. 换行：添加一个注释空行
4. 预格式化（示例代码）：行首缩进
5. 在`package`, `const`, `type`, `func`等关键字上面并且紧邻关键字的注释才会被展示
    ```go
    // 此行注释被省略

    // 此行注释被展示 
    // 
    // 此行注释被展示2 
    package banana
    ```
5. `type`, `const`, `func`以名称为注释的开头, package以Package name为注释的开头
    ```go
    // Package banana ...
    package banana

    // Xyz ...
    const Xyz = 1

    // Abc ...
    type Abc struct {}

    // Bcd ...
    func Bcd() {}
    ```
6. package注释应不超过三行， 如果超过三行，应放到`doc.go`中
7. 如果有多个package注释，按照文件名排序显示， 最多显示523字节

## Godoc
用途及用法于`go doc`类似，但可用于http服务器，方便文档查看。
### 安装
```bash
go install golang.org/x/tools/cmd/godoc@latest
```

### 使用方法
```bash
godoc -http :8080 --index -play
```
然后浏览器访问`http://127.0.0.1:8080`即可

## 参考文档
- [Go doc官方说明](https://golang.org/cmd/go/#hdr-Show_documentation_for_package_or_symbol)
- [Godoc官方博文](https://blog.golang.org/godoc)
- [Godoc技巧](https://godoc.org/github.com/fluhus/godoc-tricks)


