[TOC]
## Java对象和类
### Java类
Java对象的模板
类型变量
* **局部变量**：初始化在方法中，方法结束后，自动销毁。
* **成员变量**：定义在类中，方法体之外。创建对象时实例化。
* **类变量**：必须声明为static类型。
### 构造方法
至少调用一个构造方法，编译器提供一个默认的构造方法。
构造方法与类同名。
### 创建对象
使用关键字new来创建一个新对象。创建对象需要以下三步：
* __声明__：声明一个对象，包括对象名称和对象类型。
* __实例化__：使用关键字new来创建一个对象。
* __初始化__：使用new关键字，调用构造方法初始化对象。
```java
Puppy myPuppy = new Puppy("tommy");
```
### 访问实例变量和方法
### 源文件声明规则
当一个源文件中定义多个类，并且有`import`语句和`package`语句时，注意一下规则：
* 一个源文件中只能有一个public类，但可以有多个非public类。
* 源文件的名称应该和public类的类名保持一致。
* 如果一个类定义在某个包中，那么package语句应该在源文件的首行。
* 如果源文件包含import语句，那么应该放在package语句和类定义之间。如果没有package语句，那么import语句应该在源文件中最前面。
* import语句和package语句对源文件中定义的所有类都有效。在同一源文件中，不能给不同的类不同的包声明。
### Java包
包主要用来对类和接口进行分类。
### import语句
import语句用来提供一个合理的路径，使得编译器可以找到某个类。

***
## Java基本数据类型
* 内置数据类型
* 引用数据类型
### 内置数据类型
Java提供了八种基本类型。六种数字类型（四个整数型、两个浮点型）、一种字符类型和一种布尔型。
* byte
* short
* int
* long
* float
* double
* boolean
* char
### 引用类型
* 引用类型的变量类似于C中的指针。引用类型指向一个对象。
* 对象、数组都是引用数据类型。
* 所有引用类型的默认值都是null。
* 一个引用变量可以用来引用任何与之兼容的类型。
### Java常量
使用`final`关键字来修饰常量
```java
final double PI = 3.1415926;
```
### 自动类型转换
#### 强制类型转换
#### 自动类型转换
#### 隐含强制类型转换

***
## Java变量类型
Java支持的变量类型：
* 类变量：独立于方法之外的变量，用static修饰。
* 实例变量：独立于方法之外的变量，不使用static修饰。
* 局部变量：类的方法中的变量。
```java
public class Variable
{
    static int allClicks = 0;       //类变量
    String str = "hello world";     //实例变量
    public void method()
    {
        int i = 0;      //局部变量
    }
}
```
### Java局部变量
* 声明于方法、构造方法或者语句块中
* 在方法、构造方法或者语句块执行时创建、执行完成后，变量被销毁
* 访问修饰符不能用于局部变量
* 只在其声明区域内可见
* 栈上分配
* 无默认值，需要初始化后才能使用
### 实例变量
* 声明在类中，但是在方法、构造方法和语句块之外
* 对象实例化后，实例变量的值也就确定了
* 在对象创建时创建，在对象销毁是销毁。
* 其值需要至少被一个方法、构造方法或者语句块引用，才能使得外界通过这些方式获取到实例变量的值。
* 实例变量可以声明在使用前或者使用后。
* 访问修饰符可以修饰实例变量。
* 实例变量对于类中的方法、构造方法或者语句块可见。
* 实例变量有默认值。
* 实例变量可以通过变量名访问，但在静态方法以及其他类中，就应该使用完全限定名`ObjectReference.VariableName`。
### 类变量（静态变量）

***
## Java修饰符
* 访问修饰符
* 非访问修饰符

### 访问控制修饰符
* __default__（缺省，什么也不写）：在同一个包内可见。使用对象：类、接口、变量、方法。
* __private__：在同一个类内可见。使用对象：变量、方法。__注意：不能修饰类__。
* __public__：对所有类可见。
* __protected__：对同一包内的类和所有子类可见。__注意：不能修饰类__。
#### 默认访问修饰符-不使用任何关键字
对同一个包内的类可见。  
接口里的变量都隐式声明为`public static final`，而接口里的方法在默认情况下的访问权限为`public`。
#### 私有访问修饰符-private
声明为private的方法、变量和构造方法只能被所属类访问，类和接口不能声明为private。
#### 公有访问修饰符-public
被声明为public的类、方法、构造方法和接口能够被任何其他类访问。
#### 受保护的访问修饰符-protected
* 子类与基类在同一个包中：被声明为protected的变量、方法和构造器能被同一个包内的任何其他类访问；
* 子类与基类不在一个包中：在子类中，子类实例可以访问其从基类继承来的protected访问，而不能访问基类实例的protected方法。
接口及接口的成员变量和成员方法不能声明为protected。
***protected是Java最难理解的类成员访问权限修饰词***
#### 访问控制和继承
方法继承的规则：
* 父类中声明为public的方法在子类中必须为public。
* 父类中声明为protected的方法在子类中要么声明为protected，要么声明为public，不能声明为private。
* 父类中声明为private的方法不能被继承。

### 非访问控制符
#### static修饰符
* **静态变量**：声明独立于对象的静态变量，无论类实例多少个对象，静态变量只有一份拷贝。静态变量也称为类变量。局部变量不能被声明为static变量。
* **静态方法**：声明独立于对象的静态方法。静态方法不能使用类的非静态变量。静态方法从参数列表得到数据。
#### final修饰符
* final常量：必须显式指定初始值。通常与static修饰符一起使用来创建常量。
* final方法：类中的final方法可以被子类继承，但不能被子类修改。
* final类：final类不能被继承。
#### abstract修饰符
* 抽象类
> 抽象类不能用来实例化对象，声明抽象类的唯一目的是在将来对该类进行扩充；
> 一个类不能同时被abstract和final修饰；
> 如果一个类包含抽象方法，该类就必须被声明为抽象类。
* 抽象方法
> 抽象方法是一种没有任何实现的方法，该方法的具体实现由子类提供。
> 抽象方法不能被声明为final和static。
> 任何继承抽象类的子类必须实现该父类的所有抽象方法，除非该子类也是抽象类。
> 抽象方法的声明必须以分号为结尾，例如`public abstract sample();`。
#### synchronized修饰符
synchronized关键字修饰的方法同时间只能被一个线程访问。
#### transient修饰符
序列化对象包含被transient修饰的实例变量是，JVM跳过该特定的变量。
#### volatile修饰符
volatile修饰的成员变量在每次被线程访问时，都强制从共享内存中重新读取该成员变量的值。当成员变量发生变化时，会强制线程将变化值写到共享内存。***在任何时刻，两个不同线程总是看到某个成员变量的同一个值***。

***
## Java运算符

***
## Java循环结构

***
## Java条件语句

***
## Java switch case语句

***
## Java Number & Math类
包装类（Integer、Long、Byte、Double、Float、Short）都是抽象类Number的子类。
### Java Math类
### Number & Math类方法

***
## Java Character类
```java
char ch = 'a';
Character ch = new Character('a');
```
***char->Character：装箱***
***Character->char：拆箱***
### 转义序列
### Character方法
1. `isLetter()`
2. `isDigit()`
3. `isWhitespace()`
4. `isUpperCase()`
5. `isLowerCase()`
6. `toUpperCase()`
7. `toLowerCase()`
8. `toString()`

***
## Java String类
### 创建字符串
String类是不可改变的，如果需要对字符串进行很多的修改，应当使用StringBuffer & StringBuilder类。
### 字符串长度
`length()`方法
### 连接字符串
```java
string1.concat(string2);        //返回string2连接string1的新字符串：string1string2
```
常用使用`+`操作符。
### 创建格式化字符串
### String方法

***
## Java StringBuffer和StringBuilder类
StringBuffer类和StringBuilder类的对象能够被多次修改，且不会产生新的未使用对象。  
StringBuilder的方法**不是线程安全的**（不能同步访问）。  
StringBuild相较于StringBuffer有速度优势，因此多数情况下使用StringBuilder类。  
要求线程安全的情况下，必须使用StringBuffer类。  
### StringBuffer方法

***
## Java数组
### 声明数组变量
```java
dataType[] arrayRefVar;     //首选的方法
dataType arrayRefVar[];
```
### 创建数组
使用new操作符：
```java
arrayRefVar = new dataType[arraySize];
```
将声明与创建数组使用一条语句完成：
```java
dataType[] arrayRefVar = new dataType[arraySize];
```
或者：
```java
dataType[] arrayRefVar = {value0, value1, ..., valuek};
```
### 处理数组
通常使用基本循环或者for-each循环。  
### for-each循环
```java
double[] myList = {1.9, 2.9, 3.4, 3.5};
for(double element: myList)
{
    dosomething();
}
```
### Arrays类
* 给数组赋值：fill方法。
* 对数组排序：sort方法，升序。
* 比较数组：equals方法。
* 查找数组元素：binarySearch方法，二分查找。

***
## Java日期时间
### 获取当前日期时间
使用Date对象的toString()方法。
### 日期比较
### 使用SimpleDateFormat格式化日期
```java
Date date = new Date();
SimpleDateFormat ft = new SimpleDateFormat("yyyy-MM-dd hh:mm:ss");
System.out.println(ft.format(date));
```
### 日期和时间的格式化编码
### 使用printf格式化日期
### 解析字符串为时间
### Java休眠（sleep）
### Calendar类

***
## Java正则表达式

***
## Java方法
### 方法的定义
```
修饰符 返回值类型 方法名(参数类型 参数名)
{
    方法体
    return 返回值;
}
```
### 方法调用
1. 当方法返回一个值的时候，方法调用通常被当做一个值。
2. 当方法返回值是void，方法调用一定是一条语句。例：`System.out.println("...");`
### void关键字
### 通过值传递参数
### 方法的重载
### 构造方法
构造方法用来初始化该对象。构造方法和它所在的类对的名字相同，但构造方法没有返回值。
### 可变参数
在方法声明中，在指定参数类型后加一个省略号（...）。  
一个方法只能指定一个可变参数，且必须是最后一个参数。任何普通参数必须在它之前声明。
### finalize()方法
finalize方法在对象被回收前调用，用于清除回收对象。  
```java
/*protected确保finalize方法不会被类以外的代码调用*/
protected void finalize()
{
    //在这里终结代码
}
```

***
## Java流（Stream）、文件（File）和IO
java.io包几乎包含了所有的操作输入、输出的类。
### 读取控制台输入
### 从控制台读取多字符输入
### 从控制台读取字符串
```java
public static void main(String[] args) throws IOException
{
    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    String tmp;
    tmp = br.readLine();
    System.out.println(tmp);
}
```
### 读取文件
#### FileInputStream
从文件中读取数据。  
```java
InputStream f = new FileInputStream("C:/java/hello");
```
或者
```java
File f = new File("C:/java/hello");
InputStream out = new FileInputStream(f);
```
#### FileOutputStream
创建一个文件并向文件中写入数据。  
构造方法同上。  
### 文件和I/O
### Java中的目录
#### 创建目录
File类有两个方法创建文件夹：
* `mkdir()`方法创建一个文件夹。
* `mkdirs()`方法创建一个文件夹和它的所有父文件夹。
#### 读取目录
#### 删除目录或文件

***
## Java Scanner类
通过Scanner类获取用户的输入。  
```java
Scanner s = new Scanner(System.in);
```
通过`next()`与`nextLine()`方法获取输入的字符串。读取前一般使用`hasNext()`与`hasNextLine()`判断是否还有输入的数据。  
> **next()与nextLine()的区别：**
> * next()以空白作为结束符或者分隔符；nextLine()以Enter作为结束符。
> * next()不能得到带空格的字符串；nextLine()可以获取空白。

***
## Java异常处理
理解Java异常处理，需要掌握三种类型的异常：
* __检查性异常：__ 用户错误或者问题引起的异常，程序员无法预见。
* __运行时异常：__ 可能被程序员避免的异常。
* __错误：__ 错误不是异常，是脱离程序员控制的问题。
### Exception类的层次
所有异常类都是从java.lang.Exception类继承的子类。  
Exception类是Throwable类的子类。Throwable的另一个子类是Error。  
Exception类有两个主要子类：IOException类和RuntimeException类。
### Java内置异常类
### 异常方法
### 捕获异常
使用try/catch关键字捕获异常。
### 多重捕获块
一个try代码块后跟随多个catch代码块。
### throw/throws关键字
如果一个方法没有捕获到一个检查性异常，那么该方法必须使用throws关键字来声明。throws关键字放在方法签名的尾部。  
一个方法可以抛出多个异常。
### finally关键字
finally关键字用来创建在try代码块后执行的代码块。  
无论是否发生异常，finally代码块中的代码总会被执行。  
### 声明自定义异常
* 所有异常都必须是Throwable的子类。
* 检查类异常需要继承Exception类。
* 运行类异常需要继承RuntimeException类。
### 通用异常
* JVM异常
* 程序级异常

***
## Java继承
### 继承的概念
Java不支持多继承（C同时继承A和B），但支持多重继承（B继承A，C继承B）。  
### 继承的特性
* 子类拥有父类的非private的属性和方法。
* 子类可以对父类进行扩展。
* 子类可以用自己的方式实现父类的方法。
* Java的继承是单继承，但可以多重继承。___Java继承区别于C++继承的一个特性___。
* 提高了类之间的耦合（缺点）。
### 继承关键字
所有的类都是继承与java.lang.Object，当一个类没有继承的这两个关键字，则默认继承object祖先类。
#### extends关键字
extends只能继承一个类。
#### implements关键字
变相使得java具有多继承性，使用范围为类继承接口的情况，可以同时继承多个接口。
```java
public interface A
{
    public void eat();
    public void sleep();
}

public interface B
{
    public void show();
}

public class C implements A,B
{
    ...
}
```
#### super与this关键字
super：我们可以通过super关键字来实现对父类成员的访问，引用当前对象的父类。  
this：指向自己的引用。  
#### final关键字
final关键字声明类不能定义为继承的。
### 构造器
子类不继承父类的构造器，只是调用。  
如果父类的构造器带参数，则必须在子类的构造器中显式通过`super`关键字调用父类构造器，如果父类构造器无参数，则无需使用`super`关键字，系统会自动调用父类的无参构造器。  

***
## Java重写（Override）与重载（Overload）
### 重写（Override）
重写是子类对父类的允许访问的方法的实现过程进行重写编写，返回值和形参不能改变。**外壳不变，核心重写**。
#### 方法重写规则
* 参数列表必须完全相同。
* 返回类型可以不相同，但必须是父类返回值的派生类。
* 访问权限不能比父类中被重写的方法的访问权限更低。
* 父类的成员方法只能被它的子类重写。
* 声明为final的方法不能被重写；声明为static的方法不能被重写，但能够被再次声明。
* 子类和父类在同一个包里，子类可以重写父类所有的方法（除private和final）；如果不在一个包里，子类只能重写父类声明为public和protected的非final方法。
*  重写的方法能够抛出任何非强制异常。
* 构造方法不能够被重写。
* 如果不能继承一个方法，则不能重写这个方法。
#### super关键字的使用
调用父类的被重写方法，使用super关键字。  
### 重载（Overload）
在一个类中，方法名字相同，而参数不同。返回类型可以相同也可以不相同。  
每个重载的方法必须有独一无二的参数类型列表。  
**重载规则：**
* 必须改变参数列表；
* 可以改变返回类型；
* 可以改变访问修饰符；
* 可以声明新的或更广的检查异常；
* 方法能够在同一个类或者一个子类中被重载；
* 无法以返回值的类型作为重载函数的区分标准。
### 重写和重载的区别
| 区别点 | 重载方法 | 重写方法 |
| ---- | ---- | ---- |
| 参数列表 | 必须修改 | 一定不能修改 |
| 返回类型 | 可以修改 | 一定不能修改 |
| 异常 | 可以修改 | 可以减少或者删除，一定不能抛出新的或者更广的异常 |
| 访问 | 可以修改 | 一定不能做更严格的限制 |
### 总结
重写和重载是Java多态性的不同表现，重写是**父类与子类之间**多态性的一种表现，重载可以理解为是多态的具体表现形式。

***
## Java多态
多态是同一个接口，使用不同的实例而执行不同操作。
**多态的优点**
**多态存在的三个必要条件**
* 继承
* 重写
* 父类引用指向子类对象。例：`Parent p = new Child();`。
### 虚函数
虚函数的存在是为了多态。  
Java中没有虚函数的概念，普通函数就相当于C++的虚函数，动态绑定是Java的默认行为。使用final关键字变成非虚函数。
### 多态的实现方法
**方式一：** 重写
**方式二：** 接口
**方式三：** 抽象类和抽象方法

***
## Java抽象类
如果一个类中没有包含足够的信息来描述一个具体的对象，这样的类就是抽象类。  
抽象类不能实例化对象，其他功能依然存在。  
抽象类不能实例化对象，因此必须被继承，才能被使用。  
### 抽象类
使用abstract class来定义抽象类。
### 继承抽象类
通过一般的方式继承抽象类
### 抽象方法
该方法的具体实现由它的子类确定。  
使用abstract关键字声明抽象方法，抽象方法只有一个方法名，没有方法体。  
* 如果一个类包含抽象方法，该类就必须是抽象类。
* 任何子类都必须重写父类的抽象方法，或者声明自身为抽象类。
### 抽象类总结规定
1. 抽象类不能被实例化。
2. 抽象类中不一定有抽象方法，但包含抽象方法的类一定是抽象类。
3. 抽象类中的抽象方法只是声明，不包含方法体。
4. **构造方法，类方法（static修饰）** 不能声明为抽象方法。
5. 抽象类的子类必须给出抽象类的抽象方法的具体实现，除非该子类也是抽象类。

***
## Java封装
一种将抽象性函式接口的实现细节部分包装、隐藏起来的方法。  
### 实现Java封装的步骤
1. 修改属性的可见性来限制对属性的访问（一般为private）。
2. 对每个值属性提供对外的公共方法访问。

***
## Java接口
**接口与类的相似点：**
* 一个接口可以有多个方法。
* 接口文件保存在.java文件中，文件名使用接口名；字节码保存在.class文件中。

**接口和类的区别：**
* 接口不能实例化对象。
* 接口没有构造方法。
* 接口中的所有方法都必须是抽象方法。
* 接口不能包含成员变量，除了static和final变量。
* 接口不是被类继承，而是要被类实现。
* 接口支持多继承。

**接口特性：**
* 接口中的方法被 ___隐式指定___ 为`public abstract`。
* 接口中可以有变量，但会被 ___隐式指定___ 为`public static final`变量。
* 接口中的方法不能在接口中实现，只能由实现接口的类来实现接口中的方法。

**抽象类和接口的区别：**
* 抽象类的方法可以有方法体。
* 抽象类的成员变量可以是各种类型，但接口的成员变量只能是public static final类型。
* 接口中不能有静态代码块和静态方法。
* 一个类只能继承一个抽象类，但一个类可以实现多个接口。

### 接口的声明
```java
[可见度] interface 接口名称 [extends 其他接口名]
{
    //声明变量
    //抽象方法
}
```
### 接口的实现
类实现接口的时候，必须实现接口中的所有方法。否则必须声明为抽象的类。  
类使用`implements`关键字实现接口。  
重写接口声明的方法时，注意一下规则：  
* 不能抛出强制性异常。
* 保持一致的方法名，保持相同或相兼容的返回值类型。
* 抽象类没必要实现该接口的方法。

实现接口注意的规则：  
* 一个类可以同时实现多个接口。
* 一个接口可以继承另一个接口。
### 接口的继承
使用`extends`关键字。   
### 接口的多继承
在Java中，接口允许多继承。  
### 标记接口
标记接口是没有任何方法和属性的接口。  
使用标记接口的目的：  
* 建立一个公共的父接口
* 向一个类中添加数据类型
### 总结
___什么时候使用抽象类和接口___：  
* 拥有一些方法，并想让它们中的一些有默认实现，则使用抽象类。
* 如果想实现多重继承，必须使用接口。
* 如果基本概念在不断改变，就需要使用抽象类。（否则更改功能就需要改变所有实现了该接口的类）

---
## Java包（package）
更好地组织类，提供包机制，区别于类名的命名空间。  
__包的作用__
* 把功能相似或相关的类或接口组织在一个包中，方便类的查找和使用。
* 包采用树形存储方式。
* 包也限定了访问权限。
```java
package net.java.util;
public class Something
{
    ...
}
```
其路径应该是net/java/util/Something.java。  
### 创建包
包声明应该在源文件的第一行，每个源文件只能有一个包声明。  
### import关键字
使用`import`关键字导入包。  
在源文件中，`import`语句应该在`package`语句之后，在所有的类的定义之前。  
### package的目录结构

---
## Java数据结构
### 枚举（Enumeration）
### 位集合（BitSet）
位结合类实现了一组可以单独设置和清除的位或标志。  
### 向量（Vector）
### 栈（Stack）
### 字典（Dictionary）
字典类是一个抽象类，定义了键映射到值的数据结构。  
### 哈希表（Hashtable）
### 属性（Properties）

---
## Java集合框架

---
## Java泛型
泛型的本质是参数化类型。  
### 泛型方法
定义泛型方法的规则：  
* 所有泛型方法声明都有一个类型参数声明部分，该类型参数声明部分在方法返回类型之前。
* 类型参数只能代表引用型类型，不能是原始类型（int、double和char等）。  

有界的类型参数（限制被允许传递到一个类型参数的类型种类范围）：  
首先列出类型参数的名称，后跟`extends`关键字，最后紧跟它的上界。  
### 泛型类
在类名后面添加类型参数声明部分。  
### 类型通配符

---
## Java序列化
对象序列化机制，一个对象可以被表示为一个字节序列。  
一个对象想要序列化成功，必须：  
* 必须实现`java.io.Serializable`对象。
* 所有属性必须是可序列化的。如果某个属性不是可序列化的，必须注明是短暂的`transient`（使属性不被序列化）。
### 序列化对象
`ObjectOutputStream`类来序列化一个对象。
### 反序列化对象

---
## Java网络编程
### Socket编程
### ServerSocket类的方法
`ServerSocket`类的四个构造方法：  
1. `public ServerSocket(int port) throws IOException`
创建绑定到特定端口的服务器套接字。
2. `public ServerSocket(int port, int backlog) throws IOException`
利用指定的backlog创建服务器套接字并将其绑定到指定的本地端口号。  
3. `public ServerSocket(int port, int backlog, InetAddress address) throws IOException`
使用指定的端口、侦听backlog和要绑定到的本地IP地址创建服务器。
4. `public ServerSocket() throws IOException`
创建非绑定服务器套接字

`ServerSocket`类常用方法
1. `public int getLocalPort()`
返回此套接字在其上侦听的端口。
2. `public Socket accept() thorws IOException`
侦听并接受到此套接字的连接。
3. `public void setSoTimeout(int timeout)`
通过指定超时值启用/禁用SO_TIMEOUT，以毫秒为单位。
4. `public void bind(SocketAddress host, int backlog)`
将ServerSocket绑定到特定地址（IP地址和端口号）。
### Socket类的方法
`Socket`类有五个构造方法：
1. `public Socket(String host, int port) throws UnknownHostException, IOException`
2. `public Socket(InetAddress host, int port) throws IOException`
3. `public Socket(String host, int port, InetAddress localAddress, int localPort) throws IOException`
4. `public Socket(InetAddress host, int port, InetAddress localAddress, int localPort) throws IOException`
5. `public Socket()`

---
## Java多线程编程
### 线程的生命周期


