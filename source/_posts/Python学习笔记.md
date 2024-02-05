---
title: Python学习笔记
date: 2024-02-04 17:22:00
tags:
- python
categories:
- [技术,python]
description: 
---

## strip函数

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

## split函数

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

## isdigit和isalpha函数

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
## int函数

在Python中，int()函数用于将一个字符串或数字转换为十进制整数。

当int()函数接收一个字符串作为参数时，它会尝试将这个字符串转换为整数。例如：
```python
num_str = "123"
num_int = int(num_str)
print(num_int)  # 输出: 123
```
可以使用可选的第二个参数指定字符串的进制。例如：
```python
hex_str = "1A"
decimal_val = int(hex_str, 16)
print(decimal_val)  # 输出: 26
```
当int()函数接收一个浮点数作为参数时，它会将这个浮点数截断为整数。例如：
```python
num_float = 3.14
num_int = int(num_float)
print(num_int)  # 输出: 3
```
## 字典与map

在Python中，Map可以用字典（dictionary）来表示，使用键值对来存储和操作整个映射关系。字典是一种无序的数据结构，它存储的是键值对（key-value pairs）。Map中的键是唯一的，且通常用来进行快速的查找操作。
在Python中，字典是一种无序、可变且可迭代的数据类型。字典的主要特点是使用键值对存储数据。下面详细介绍字典的用法：

创建字典：
字典可以使用花括号 {} 或内置的 dict() 函数创建。键值对之间使用冒号 : 分隔，每对键值对之间使用逗号 , 分隔。
```python
#创建一个空字典
my_dict = {}

#创建一个带有初始键值对的字典
my_dict = {"key1": "value1", "key2": "value2"}

#使用dict()函数创建字典
my_dict = dict(key1="value1", key2="value2")
```

访问和修改字典中的元素：
字典的每个元素都有一个键和对应的值，可以使用键来访问和修改字典中的元素。
```python
my_dict = {"key1": "value1", "key2": "value2"}

#访问字典中的元素
value1 = my_dict["key1"]
print(value1)  # 输出: value1

#修改字典中的元素
my_dict["key2"] = "new value"
print(my_dict)  # 输出: {'key1': 'value1', 'key2': 'new value'}
```

添加和删除字典中的元素：
可以使用赋值语句添加新的键值对，或使用del关键字删除指定的键值对。
```python
my_dict = {"key1": "value1"}

#添加新的键值对
my_dict["key2"] = "value2"
print(my_dict)  # 输出: {'key1': 'value1', 'key2': 'value2'}

#删除指定的键值对
del my_dict["key1"]
print(my_dict)  # 输出: {'key2': 'value2'}
```
字典的常用操作：

获取所有键：使用keys()方法获得字典中所有的键。
获取所有值：使用values()方法获得字典中所有的值。
获取所有键值对：使用items()方法获取字典中所有的键值对，返回一个可迭代的元组。
```python
my_dict = {"key1": "value1", "key2": "value2"}

#获取所有键
keys = my_dict.keys()
print(keys)  # 输出: dict_keys(['key1', 'key2'])

#获取所有值
values = my_dict.values()
print(values)  # 输出: dict_values(['value1', 'value2'])

#获取所有键值对
items = my_dict.items()
print(items)  # 输出: dict_items([('key1', 'value1'), ('key2', 'value2')])
```
## append和pop和del

append() 方法用于在列表末尾追加新的元素。
```python
#在列表末尾追加一个新元素
my_list.append(4)
print(my_list)  #输出: [1, 2, 3, 4]
```
pop() 方法用于移除列表中的一个元素（默认是最后一个），并返回该元素的值。它还可以接受一个索引作为参数，来移除指定位置的元素。
```python
my_list = [1, 2, 3, 4, 5]
#移除并返回最后一个元素
popped_element = my_list.pop()
print(popped_element)  #输出: 5
print(my_list)  #输出: [1, 2, 3, 4]
#使用索引来移除指定位置的元素
popped_element = my_list.pop(1)  #移除索引为1的元素（即第二个元素）
print(popped_element)  #输出: 2
print(my_list)  #输出: [1, 3, 4]
```
del 关键字用于从字典中删除指定键及其对应的值，删除操作不返回任何值。
```python
my_dict = {"a": 1, "b": 2, "c": 3}

#使用del关键字删除键为"a"的元素
del my_dict["a"]
print(my_dict)  # 输出: {'b': 2, 'c': 3}
```
## if-else

在Python中，常见的条件语句包括if语句、elif语句（else if的简写）和else语句。

三元运算符实现if-else的简便写法：
```python
value_if_true if condition else value_if_false
```
在Python中，可以使用连续比较来对多个条件进行组合。例如，要检查变量x是否大于10且小于20，可以这样写：
```python
x = 15
if 10 < x < 20:
    print("x is between 10 and 20")
```

