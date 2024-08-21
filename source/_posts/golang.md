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
1. 快速编译
Go 编译器非常快，可以在几秒钟内编译大规模的代码库。这是因为 Go 被设计为一种简洁且高效的编程语言，编译器能够快速解析和处理代码。

2. 跨平台编译
Go 可以轻松地为多个平台（如 Windows、MacOS、Linux、FreeBSD 等）编译二进制文件。你可以使用 GOOS 和 GOARCH 环境变量来指定目标操作系统和架构。
​
3. 静态编译
Go 生成静态链接的可执行文件，意味着运行时不需要任何外部的动态库。这使得部署 Go 应用程序非常简单，只需要拷贝可执行文件即可。

4. 内置并发支持
Go 语言原生支持并发编程，通过 goroutine 和 channel，使得编写高效并发代码变得简单。Go 编译器有效地优化和管理这些并发机制，使得程序运行更加高效。

5. 垃圾回收
Go 编译器内建了高效的垃圾回收机制（GC），自动管理内存分配和释放。现代的 Go 垃圾回收器具有低延迟和高吞吐量的特点，使得 Go 程序能够高效运行。

6. 内置工具链
Go 包含了一系列内置工具，包括格式化工具（gofmt），静态分析工具（go vet），测试工具（go test）和文档生成工具（godoc）。这些工具与编译器紧密集成，提高了开发效率和代码质量。

7. 模块化
Go 支持模块化编程（通过 go mod），使得包管理和依赖管理更加简单和高效。依赖版本控制和模块代理的支持，使得项目的构建和发布更加便捷。

8. 简洁和一致性的语法
Go 语言的设计哲学之一是简洁和一致性。其语法简单易懂，没有过多的复杂特性（如头文件、模板元编程等），使得编译器更加高效，并减少了编程和调试的复杂度。

9. 强大的标准库
Go 语言附带了一个强大的标准库，涵盖了网络编程、文件 I/O、文本处理等多种常见任务。编译器可以很好地优化和管理这些标准库，以提供高质量的性能。

10. 现代化的特性
Go 编译器和语言持续迭代，添加了许多现代化的编程特性，如泛型、错误包装等，使得程序的编写更加灵活和强大。

11. 编译器优化
Go 编译器进行多种优化，如逃逸分析、内联展开等，以提高生成代码的性能和效率。这些优化确保了 Go 程序在运行时的高效性。

## Go的程序从哪里开始运行？
> A：package main中的main函数

## fmt这个package提供了哪些功能？
> A：Go语言标准库中的一个包，用于格式化I/O
打印相关函数
格式化打印

fmt.Print(a ...interface{}) (n int, err error): 打印任意数量的变量，不附加任何额外的格式。
fmt.Println(a ...interface{}) (n int, err error): 打印任意数量的变量，并在末尾添加一个换行符。
fmt.Printf(format string, a ...interface{}) (n int, err error): 按照指定的格式字符串打印变量。
格式化生成字符串

fmt.Sprint(a ...interface{}) string: 返回格式化后的字符串。
fmt.Sprintln(a ...interface{}) string: 则返回格式化后的字符串，并在末尾添加一个换行符。
fmt.Sprintf(format string, a ...interface{}) string: 返回一个按指定格式化后的字符串。
错误输出

fmt.Fprint(w io.Writer, a ...interface{}) (n int, err error): 向指定的 io.Writer 写入格式化的字符串。
fmt.Fprintf(w io.Writer, format string, a ...interface{}) (n int, err error): 向指定的 io.Writer 写入格式化后的字符串，按照指定的格式化规则。
fmt.Fprintln(w io.Writer, a ...interface{}) (n int, err error): 将数据格式化后写入 io.Writer，并在末尾添加一个换行符。
读取相关函数
从标准输入读取

fmt.Scan(a ...interface{}) (n int, err error): 从标准输入读取空格分隔的值写入到提供的变量中。
fmt.Scanln(a ...interface{}) (n int, err error): 从标准输入读取值，直到遇到换行符。
fmt.Scanf(format string, a ...interface{}) (n int, err error): 从标准输入读取格式化的文本，并将其写入提供的变量中。
从特定输入读取

fmt.Fscan(r io.Reader, a ...interface{}) (n int, err error): 从指定的 io.Reader 读取数据。
fmt.Fscanln(r io.Reader, a ...interface{}) (n int, err error): 从指定的 io.Reader 读取数据直到换行符。
fmt.Fscanf(r io.Reader, format string, a ...interface{}) (n int, err error): 从指定的 io.Reader 读取格式化数据。
从字符串读取

fmt.Sscan(str string, a ...interface{}) (n int, err error): 从字符串读取。
fmt.Sscanln(str string, a ...interface{}) (n int, err error): 从字符串读取直到换行符。
fmt.Sscanf(str string, format string, a ...interface{}) (n int, err error): 从字符串读取格式化数据。
格式化标志
fmt 包使用特定的格式化标志来指定输出格式，比如：

%d：十进制整数
%s：字符串
%f：浮点数
%t：布尔值
%v：按默认格式输出值
%#v: 值的 Go 语法表示
%T：输出值的类型
%p：指针
%%：字面上的百分号
这些函数和格式化标志提供了非常强大的功能，使得 fmt 包成为了 Go 语言中处理文本格式化和输入输出的核心工具之一。

## 左花括号{放在哪里不会引起语法错误？
> A: 左花括号需要与func同一行，右花括号需要单独一行
> R: 左花括号必须与函数名或方法名在同一行在，Go 语言中，左花括号 { 一般要求与相关关键词（如 func、if、for、switch 等）在同一行。这不仅提高了代码的一致性和可读性，还有助于团队协作和代码审查。 并且，使用 gofmt 工具可以自动完成这些格式化工作，确保代码风格的一致性

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
//fmt.Println函数用于打印并在最后加一个换行符因此不用在第一个Hello World后边加\n，这样会有额外空行
//如果想加/n可以这样
fmt.Println("Hello, World\nHello")
//编译程序并运行
go run hello.go
//先编辑、再运行
go build hello.go
./hello