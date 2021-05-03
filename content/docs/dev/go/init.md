---
title: "Init--初始化函数"
weight: 3
bookFlatSection: false
bookToc: true
bookHidden: false
bookCollapseSection: false
bookComments: false
---

<!--more-->

## 作用
- 初始化不能采用初始化表达式初始化的变量。
- 程序运行前的注册。
- 实现sync.Once功能。

## 规则
- 先于main函数自动执行。
- 不能被其他函数调用。
- 没有输入参数、返回值。
- 每个包可以有多个init函数。
- 包的每个源文件也可以有多个init函数。
- 同一个包的init执行顺序，golang没有明确定义。
- 不同包的init函数按照包导入的依赖关系决定执行顺序。

##  备注
- 设置`GODEBUG`环境变量: `inittrace=1`，可以在运行时会为每个包的 init 打印一行标准错误信息，总结其执行时间和内存分配。
- 若只想调用该包的init函数，不使用包导出的变量或者方法，可使用类似以下方法导入：
    ```go
    import _ "net/http/pprof"
    ```
