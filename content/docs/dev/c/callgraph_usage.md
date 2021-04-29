---
title: "函数调用树生成器--Callgraph"
weight: 1
bookFlatSection: false
bookToc: true
bookHidden: false
bookCollapseSection: false
bookComments: false
---
## 介绍
Callgraph 是一个生成C代码函数调用树的工具，与以下三个工具配合使用：
- cflow/calltree: 用于生成 C 函数调用树
- graphviz: 处理 dot 文本图形语言
- tree2dotx: 用于把 C 函数调用树转换为 dot 格式的脚本

## 安装 
Environment: Ubuntu 20.04
```bash
sudo apt-get install cflow graphviz
```
接下来安装 tree2dotx 和 Callgraph，这里都默认安装到 `/usr/local/bin`。
```bash
sudo wget -c https://github.com/tinyclub/linux-0.11-lab/raw/master/tools/tree2dotx -o /usr/local/bin/tree2dotx
sudo wget -c https://github.com/tinyclub/linux-0.11-lab/raw/master/tools/callgraph -o /usr/local/bin/callgraph
sudo chmod +x /usr/local/bin/{tree2dotx,callgraph}
```

## 使用
```bash
callgraph -f main -d ./file.c -F "printf print" -D 2 -b firefox 
```
> -f: 指定目标函数
> 
> -d: 指定函数所在文件（或者指定函数搜索路径）
> 
> -F: 指定不感兴趣的分支
> 
> -D: 指定生成调用树的深度
> 
> -b: 指定打开方式
