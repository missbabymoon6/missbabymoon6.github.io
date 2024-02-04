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
1.[strip()、lstrip()、rstrip()函数](#striplstriprstrip函数)  
2.[异常处理](#异常处理)
3.[split()函数](#split函数)
4.[isdigit和isalpha函数](#isdigit和isalpha函数)

## strip()、lstrip()、rstrip()函数

在Python中，strip()函数是用于去除字符串头尾的指定字符（默认为空白字符如：空格、换行符\n、制表符\t、\r、\x0b、\x0c）或字符序列。该函数不会改变原字符串，而是返回一个新的去除了指定字符的字符串。

strip()函数可以接受一个可选的参数，用于指定要去除的字符或字符序列。
例如：
```python
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
```
在上面的例子中，第一个strip()函数去除了字符串s头尾的空格，而第二个strip()函数去除了字符串s头尾的#字符。
同样lstrip()方法用于去除字符串左侧（开头）的指定字符，rstrip()方法则用于去除字符串右侧（末尾）的指定字符。

## 异常处理

在Python中，异常是程序运行时可能发生的错误情况。Python使用异常处理来优雅地处理这些错误，而不是直接导致程序崩溃。异常处理是一种用于捕获、处理和报告代码中错误的机制。异常处理通过以下关键字实现：

try: 用于包裹可能引发异常的代码块。
except: 用于捕获指定类型的异常，并提供处理代码。
else: 可选的子句，用于在try块没有引发异常时执行的代码。
finally: 可选的子句，无论是否引发了异常都会执行的清理代码。

以下是异常处理的基本结构和用法：
```python
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
## split()函数
在Python中，split()是一个字符串对象的方法，它用于将一个字符串按照指定的分隔符拆分成多个子串，并将这些子串组成一个列表返回。split()方法的基本语法如下：

```python
string.split(separator, maxsplit)
```
separator 是用于指定分隔符的字符串，如果省略，则默认按照空格进行分割。
maxsplit 是指定分割的次数，如果有指定，最多分割 maxsplit - 1 次，剩余部分作为最后一个元素输出。
以下是一些使用split()方法的示例：
```python
#使用空格分割字符串
s = "apple orange banana"
words = s.split()
print(words)  # ['apple', 'orange', 'banana']

#使用逗号分割字符串
s = "apple,orange,banana"
fruits = s.split(',')
print(fruits)  # ['apple', 'orange', 'banana']

#最多分割两次
s = "apple,orange,banana,grape"
result = s.split(',', 2)
print(result)  # ['apple', 'orange', 'banana,grape']
```
split()方法非常实用，可以方便地将字符串按照指定的规则分割成多个部分，使用起来十分灵活。

## isdigit()和isalpha()函数
在Python中，可以使用isdigit()方法来判断一个字符是否是数字，使用isalpha()方法来判断一个字符是否是字母。这两个方法分别返回布尔值True或False。
例如：
```python
char = 'A'
if char.isdigit():
    print("字符是数字")
elif char.isalpha():
    print("字符是字母")
else:
    print("字符不是数字也不是字母")
```

