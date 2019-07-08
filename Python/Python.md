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
下标索引，方括号截取。  
### 更新列表
数据项的修改和更新。  
使用`append()`方法添加列表项。  
### 删除列表元素
使用`del`语句删除列表的元素。  
### 嵌套列表

---
## Python3元组
元组的元素 _不能修改_。  
元组使用小括号。  
___元组只含有一个元素时，需要在元素后面添加逗号。___  
```python
tup1 = (50,);
```
### 访问元组
下标索引访问。  
### 修改元组
元组的元素值不允许修改，但可以将多个元组进行连接组合。  
### 删除元组
元组的元素不允许删除，但可以使用`del`语句删除整个元组。  

---
## Python3字典
键值对用冒号分割，每个对用逗号分割，整个字典包在花括号中。  
键必须唯一，且不可变。  
### 访问字典里的值
把相应的键放到方括号中。  
### 修改字典
增加新的键值对，修改或删除已有的键值对。  
### 删除字典元素
能删除单一元素，也能清空字典，也能删除字典。  
```python {.line-numbers}
del dict["Name"];       #删除键
dict.clear();       #清空字典
del dict;       #删除字典
```
字典键的特性  
1. 不允许同一个键出现两次。
2. 键必须不可变。

---
## Python3集合
_无序_ 的 _不重复_ 元素序列。  
使用`{}`或者`set()`函数创建，但空集必须使用`set()`。  
### 集合基本操作
1. 添加元素
`s.add(x);`或者`s.update(x);`。
2. 移除元素
`s.remove(x);`或者`s.discard(x);`。
`s.pop()`随机删除一个元素。  
3. 计算集合元素个数
`len(s);`
4. 清空集合
`s.clear()`
5. 判断元素是否在集合中存在

---
## Python3条件控制
### if语句
1. 每个条件后面要使用`:`。
2. 使用缩进划分语句块。
3. Python中没有switch-case语句。
### if嵌套

---
## Python3循环语句
### while循环
```
while 判断条件：
    语句
```
while循环使用else语句，在条件为false时执行else语句块。  
### for语句
```
for <variable> in <sequence>:
    <statements>
else:
    <statements>
```
### range()函数
遍历数字序列，使用内置的`range()`函数。  
### break和continue语句及循环中的else子句
`break`语句可以跳出for和while循环体。  
`continue`语句跳出当前循环块中剩余的语句，直接进行下一次循环。  
`else`语句在穷尽列表或条件变为false导致循环终止而被执行。但循环被break时不执行。  
### pass语句
占位语句，不做任何事。  

---
## Python3迭代器与生成器
### 迭代器
访问集合元素的一种方式。  
迭代器只能往前不会后退。  
两个基本方法：`iter()`和`next()`。  
字符串、列表和元组对象都可以用于创建迭代器。  
### 生成器
使用`yield`函数成为生成器（generator）。  

---
## Python3函数
### 定义一个函数
```
def 函数名(参数列表):
    函数体
```
### 函数调用
### 参数传递
Python中，类型属于对象，变量是没有类型的。  
#### 可更改与不可更改对象
* __不可变类型__：原有变量被重新赋值后，是丢弃之前的值，而不是改变值。
* __可变类型__：直接修改内部的值。

Python函数的参数传递：  
* __不可变类型__：类似于值传递。只传递变量的值，不对变量本身产生影响。
* __可变类型__：类似于引用传递。外部的原变量会被影响。
### 参数
* 必需参数：需以正确的顺序传入函数。
* 关键字参数：使用关键字参数来确定传入的参数值。不需要指定顺序。
```python
printinfo(age=50, name="runoob")
```
* 默认参数：如果没有传递参数，则会使用默认参数。
在函数定义时就使用一个默认参数。  
___默认参数必须放在最后___  
```python
def printinfo(age, name="yao")
```
* 不定长参数：使用加`*`的参数，以元组的形式传入。
使用`**`以字典形式传入。  
### 匿名函数
使用lambda表达式创建匿名函数。  
```
lambda [arg1 [,arg2,.....argn]]:expression
```
### return语句
### 变量作用域
* L 局部作用域
* E 闭包函数外的函数中
* G 全局作用域
* B 内置作用域
### 全局变量和局部变量
#### global和nolocal关键字
___函数内可以访问全局变量，但不能修改其值！___  
当内部作用域想修改外部作用域的变量时，使用`global`和`nolocal`关键字。  

---
## Python3数据结构
### 列表
___列表可以修改，但字符串和元组不能___  
### 将列表当做堆栈来使用
### 将列表当做队列使用
效率不高。  
### 列表推导式
### 嵌套列表解析
### del语句
### 元组和序列
元组在输出时总是有括号的。  
### 集合
### 字典
### 遍历技巧

---
## Python3模块
### import语句
### form...import语句
### __name__属性
使用`__name__`属性来使该程序块仅在该模块自身运行时执行。  
### dir()函数
`dir()`函数可以找到模块内定义的所有名称。  
### 标准模块
### 包
管理Python模块命名空间的形式，采用“点模块名称”。  

---
## Python3输入输出
### 输出格式美化
### 读取键盘输入
`input()`内置函数从标准输入读入一行文本。  
### 读和写文件
`open()`将返回一个file对象。  
```python
open(filename, mode)
```
### 文件对象的方法
#### f.read()
读取一个文件的内容，结果作为字符串或字节对象返回。  
#### f.readline()
从文件中读取单独的一行。  
#### f.readlines()
读取文件的所有行。可设置参数。  
#### f.write()
将string写入文件中，并返回写入的字符数。
#### f.tell()
返回文件对象当前所处的位置。
#### f.seek()
改变文件当前的位置。
#### f.close()
关闭文件，释放系统的资源。
### pickle模块
实现基本的数据序列和反序列化

---
## Python3 OS文件/目录方法

---
## Python3 错误和异常
### 语法错误
### 异常
运行时检测到的错误。
### 异常处理
### 抛出异常
使用`raise`语句抛出一个指定的异常。
### 用户自定义异常
异常继承自Exception类。
### 定义清理行为
`finally`子句
### 预定义的清理行为

---
## Python3 面向对象
### 类定义
### 类的方法
类方法必须包含参数self，且为第一个参数。  
### 继承
```
class DerivedClassName(BaseClassName1):
```
### 多继承
### 方法重写
### 类属性和方法
#### 类的私有属性
`__private_attrs`，在类内部方法使用时`self.__private_attrs`。  
#### 类的方法
使用`def`关键字定义一个方法，类方法必须包含参数`self`，且为第一个参数。
#### 类的私有方法
`__private_method`
### 运算符重载

---
## Python3 网络编程

---
## Python3 多线程
### _thread模块
```python {.line-numbers}
import _thread
import time

def print_time(threadName, delay):
    count = 0
    while count<5:
        time.sleep(delay)
        count += 1
        print("%s: %s" %(threadName, time.ctime(time.time())))

try:
    _thread.start_new_thread(print_time, ("Thread-1", 2,))
    _thread.start_new_thread(print_time, ("Thread-2", 4,))
except:
    print("Error: Canot start thread")

while 1:
    pass
```
### 线程模块
两个标准库`_thread`和`threading`提供对线程的支持。  
提供`Thread`类来处理线程。  
### 使用threading模块创建线程
从`threadiing.Thread`继承创建一个新的子类，实例化后调用`start()`启动新线程，即调用线程的`run()`方法：  
```python {.line-numbers}
import threading
import time

exitFlag = 0

class myThread(threading.Thread):
    def __init__(self, threadID, name, counter):
        threading.Thread.__init__(self)
        self.threadID = threadID
        self.name = name
        self.counter = counter
    def run(self):
        print("Begin thread: " + self.name)
        print_time(self.name, self.counter, 5)
        print("Quit thread: " + self.name)

def print_time(threadName, delay, counter):
    while counter:
        if exitFlag:
            threadName.exit()
        time.sleep(delay)
        print("%s: %s" %(threadName, time.ctime(time.time())))
        counter -= 1

thread1 = myThread(1, "Thread-1", 1)
thread2 = myThread(2, "Thread-2", 2)

thread1.start()
thread2.start()
thread1.join()
thread2.join()
print("Main thread quit")
```
### 线程同步
使用`Thread`对象的`Lock`和`Rlock`都能实现简单的线程同步，两个对象都有`acquire`方法和`release`方法。  
### 线程优先级队列
