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


