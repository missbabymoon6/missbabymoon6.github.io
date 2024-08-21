---
title: golang
date: 2024-08-21 10:54:00
tags:
- 学习笔记
categories:
- [语言]
description: 记得充电和维护：）
---
学习资料：https://www.bilibili.com/video/BV1fD4y1m7TD/?p=2&spm_id_from=pageDriver

# GO01课后作业
## Go编译器有哪些优点？

## Go的程序从哪里开始运行？
A：package main中的main函数

## fmt这个package提供了哪些功能？
A：
## 左花括号{放在哪里不会引起语法错误？
A：左花括号需要与func同一行，右花括号需要单独一行

## 编写一个程序：第一行输出Hello, World 第二行输出Hello。
```go
//hello.go
package main
import fmt//错误1

func main(){
    fmt.Println("Hello, World\n")//错误2
    fmt.Println("Hello")
}
```
R:批改：
```go
//go语言导入go标准库中的包的方法：
import "fmt"
//导入多个包：
import(
    "fmt"
)
//指定自定义包
import "package-path"
//fmt.Println函数用于打印并在最后加一个换行符
//因此不用在第一个Hello World后边加\n
//如果想加/n可以这样
fmt.Println("Hello, World\nHello")
//编译程序并运行
go run hello.go
//先编辑、再运行
go build hello.go
./hello