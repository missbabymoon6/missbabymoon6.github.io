---
title: Python学习笔记
date: 2024-02-04 17:22:00
tags:
- python
categories:
- [技术,python]
description: 
---
### strip()函数

在Python中，strip()函数是用于--去除字符串头尾的指定字符（默认为空格或换行符）或字符序列--。该函数不会改变原字符串，而是返回一个新的去除了指定字符的字符串。

strip()函数可以接受一个可选的参数，用于指定要去除的字符或字符序列。

例如：
```
s = "  Hello, World!  "
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


在上面的例子中，第一个strip()函数去除了字符串s头尾的空格，而第二个strip()函数去除了字符串s头尾的#字符。