# Python3
[TOC]

---
## Python3 基本语法
### 编码
```python {.line-numbers}
# -*- coding: cp-1252 -*-
```
### 标识符
### python保留字
### 注释
```python {.line-numbers}
#单行注释
'''
多行注释
'''
```
### 行与缩进
### 多行语句
使用反斜杠\。
### 数字（Number）类型
* int（整数）
* bool（布尔）
* float（浮点数）
* complex（复数）
### 字符串（String）

---
## Python3基本数据类型
Python变量不需要声明。  
为多个变量赋值：  
```python
a = b = c = 1;
a, b, c = 1, 2, "runoob";
```
### 标准数据类型
* Number（数字）
* String（字符串）
* List（列表）
* Tuple（元组）
* Set（集合）
* Dictionary（字典）

其中：  
* __不可变数据__：Number、String、Tuple
* __可变数据__：List、Dictionary、Set
### Number（数字）
Python3支持int、float、bool和complex。  
### String（字符串）
___Python字符串不能改变___。  
### List（列表）
* 列表中的元素的类型可以不相同，支持嵌套。  
* 列表写在`[]`中，用`,`分隔。  
* `+`是列表连接运算符，`*`是重复操作。  
* 列表的元素 ___可以改变___。  

Python列表截取支持第三个参数，截取的步长。  
### Tuple（元组）
元组的元素 ___不能修改___。  
元组写在`()`中，元素之间用`,`隔开。  
元组的元素类型也可以不相同。  
### Set（集合）
基本功能是进行成员关系测试和删除重复元素。  
使用`{}`或者`set()`创建集合，创建空集合必须用`set()`。  
### Dictionary（字典）
字典是无序的对象集合，字典中的元素通过键来存取。  
字典是一种映射类型，用`{}`标识，是无序的 __键（key）：值（value）__ 的集合。 
键必须使用 ___不可变类型___，且唯一。  
### Python数据类型转换

---
## Python3解释器

---
## Python3注释

---
## Python3运算符
### Python算术运算符
### Python比较运算符
### Python赋值运算符
### Python位运算符
### Python逻辑运算符
* and
* or 
* not
### Python成员运算符
* in
* not in
### Python身份运算符
比较两个对象的存储单元  
* is 判断两个标识符是不是引用自己的一个对象  
* is not

---
## Python3数字（Number）
数据类型是 _不允许改变_ 的，改变将重新分配内存空间。  
### Python数字类型转换
### Python数字运算
### 随机数函数
### 三角函数
### 数字常量

---
## Python3字符串
### Python访问字符串中的值
不支持单字符类型。使用`[]`截取字符串。  
### Python转义字符
### Python字符串运算符
| 操作符 | 描述 |
| --- | --- |
| \+ | |
| \* | |
| [] | 通过索引截取字符串中字符 |
| [:] | __左闭右开__ |
| in | |
| not in | |
| r/R | 原始字符串 |
|% | 格式化字符串 |
### Python三引号
允许字符串跨行。  

---
## Python3列表
### 访问列表中的值
