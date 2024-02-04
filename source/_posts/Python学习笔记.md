---
title: Python学习笔记
date: 2024-02-04 17:22:00
tags:
- python
categories:
- [技术,python]
description: 
---

# 目录
1.[strip()函数](#strip()函数)  
2.[异常处理](#异常处理)

## strip()函数

在Python中，strip()函数是用于去除字符串头尾的指定字符（默认为空格或换行符）或字符序列。该函数不会改变原字符串，而是返回一个新的去除了指定字符的字符串。

strip()函数可以接受一个可选的参数，用于指定要去除的字符或字符序列。

例如：

```s = "  Hello, World!  "
stripped_s = s.strip()
print(stripped_s)  # 输出：Hello, World!

s = "###Hello, World!###"
stripped_s = s.strip("#")
print(stripped_s)  # 输出：Hello, World!

s = "  Hello, World!  "
stripped_s = s.strip()
print(stripped_s)  # 输出：Hello, World!

s = "###Hello, World!###"
stripped_s = s.strip("#")
print(stripped_s)  # 输出：Hello, World!
```

在上面的例子中，第一个strip()函数去除了字符串s头尾的空格，而第二个strip()函数去除了字符串s头尾的#字符。

## 异常处理

在Python中，异常是程序运行时可能发生的错误情况。Python使用异常处理来优雅地处理这些错误，而不是直接导致程序崩溃。异常处理是一种用于捕获、处理和报告代码中错误的机制。异常处理通过以下关键字实现：

try: 用于包裹可能引发异常的代码块。
except: 用于捕获指定类型的异常，并提供处理代码。
else: 可选的子句，用于在try块没有引发异常时执行的代码。
finally: 可选的子句，无论是否引发了异常都会执行的清理代码。

以下是异常处理的基本结构和用法：
```
try:
    # 可能引发异常的代码
    result = 10 / 0  # 除以0会引发ZeroDivisionError异常
except ZeroDivisionError:#except 后如果没有错误类型则捕获所有类型
    # 捕获ZeroDivisionError异常
    print("除数不能为0！")
else:
    # 如果try块中没有引发异常，执行这里的代码
    print("计算结果：", result)
finally:
    # 无论是否引发了异常，都会执行这里的清理代码
    print("清理工作完成")
```
## 