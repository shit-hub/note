---
title: "Init--初始化函数"
weight: 1
bookFlatSection: false
bookToc: true
bookHidden: false
bookCollapseSection: false
bookComments: false
---

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
