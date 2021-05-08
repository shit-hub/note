---
title: "__builtin_expect使用"
weight: 3
bookFlatSection: false
bookToc: true
bookHidden: false
bookCollapseSection: false
bookComments: false
---

<!--more-->

环境要求 : GCC(version > v2.96)

## 作用
允许程序员将最有可能执行的分支告诉编译器。这样编译器可以对代码进行优化，以减少指令跳转带来的性能下降。

这个指令的写法为：`__builtin_expect(EXP, N)`。意思是：EXP==N的概率很大。

## 源码及使用方法
源码声明如下：
```c
long __builtin_expect(long exp, long c);
```
一般的使用方法是将`__builtin_expect`指令封装为`likely`和`unlikely`宏。这两个宏的写法如下.
```c
#define likely(x) __builtin_expect(!!(x), 1) //x很可能为真       
#define unlikely(x) __builtin_expect(!!(x), 0) //x很可能为假
```

## 例子
```bash
int x, y;
if(unlikely(x > 0))
    y = 1; 
else 
    y = -1;
```
