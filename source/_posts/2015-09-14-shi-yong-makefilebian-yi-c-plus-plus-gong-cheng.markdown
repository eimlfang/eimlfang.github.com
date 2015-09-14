---
layout: post
title: "使用静态Makefile编译c++工程"
date: 2015-09-14 17:59:24 +0800
comments: true
categories: 
---
Makefile的基本语法:  

````  
target: 依赖(文件或者target)
	命令
````
__命令必须在target后另起一行，并用Tab缩进。__  

例子:  
编译单个文件main.o  

````  
main.o: main.cpp
	g++ -c -Wall main.cpp
````  

为了使Makefile可读性和易用性增加，可以在Makefile中定义变量，例如我定义的
  
  ````  
PROJECT_NAME=AlgorithmLearning  
CC=g++
CFLAGS=-c -Wall
````  
这样，target声明就可以使用如下：  
  
  ````
main.o: main.cpp
	$(CC) $(CFLAGS) main.cpp
````
以上是编译单个文件的target声明，编译多个文件，可以使用:  

````  
build: (编译文件1target) （编译文件2target）...
	@echo "编译完成"

````    
这样会声称多个文件的.o文件以及一个可执行的二进制文件，在此我又创建了一个target __run__来执行这个可执行文件:  
  
  ````
  run: 
  	@echo "正在执行$(PROJECT_NAME)"
  	@./$(PROJECT_NAME)""
  ````    
  在Makefile中，我还创建了一些功能target：  
  __build__：编译工程  
  __run__：运行可执行文件  
  __clean__：清除编译生成的.o和可执行二进制文件  
  __clean_o_file__:清除.o文件  
  具体代码可在[github](https://github.com/eimlfang/Learning-cplusplus)查看
  
    
  ___这里所写的Makefile只是简单的非动态的。___  
  
  
  
  