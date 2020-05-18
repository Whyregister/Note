#？

链表藏匿函数指针伪造面向对象

数组引用

函数引用

补码

ld链接器



C++

c++ ,cprimer plus

解决软件设计的目标：
代码的复杂



IOSTREAM.H

系统
编译器
操作系统


使用new delete 代替malloc few



记事本加命令行

minGW 编译器

cd change directory(目录)

g++ -o      newname                  Hello.cpp

input output stream 流

iostream 输入输出文件

using name std；
命名空间

cout<<"hello workd" << endl(end line)

endl(重启一行)

与\n 区别

\n 纯洁 换行
endl 1.换行 2.fflush(stdin)

cout 为iostream 里 输出流代表

编译
预处理preprocessing ->.ii-> 编译compile->.s->assembly(汇编)->.o目标文件->链接->.exe

链接： 同该语言的库连接，生成特定的可执行文件

执行 

cout :输出对象

<< 插入

enterprise 
主存  main memory

随机访问储存器
randomaccess memory ,RAM

二进制 binary

bin (二进制) 
lib

8 bit = 1byte


10 mbps = 10 bit per sceond

避免重名  namespeace

变量名
1、首字母只能是下划线和字母
2、下划线字母数字
3、不能是关键字

integer

cout << INTMAX<< endle
INTMAX + #define INT_MAX 2........

char belong to int 
 char 8 bit -128 ~127

c++ 处理身份证号码

```c++
bool;型
```

```c++
size_t= typedef unsign int size_t;
```

cout 是一个对象

c++ 里的小数

float 6~7位有效数字

半径 radius；

float height = 100.3f;

控制cout 的显示精度

cout << fixed;(固定)



```c++
bool (true/false)
```

 

```c++
char16_t char 32_t
```

```c++
fixed();//固定以数字输出
setprecision(2);//控制小数位数

setconsoletitle();//窗口标题

int main()
{
	setconsoletitile ;
	/**伤害*/  //文本注释
	double value_attack =57.88;
    
	 
}





```

char 类型

1111 1111

0000 0000

1 1111111

0 0000000

符号位



```C++
cout << CHAR_MIN<<CHAR_MAN<<endl;
uchar ;//无符号
cout << CHAR_UCHAR;
```

大写小写差一个空格；

```c++
//test
cout << 'a'+1
```

cin

输入语句

```c++
int main ()
{
    int num;
    char ch1,ch2,ch3;
    cout <<"输入一个数字";
    cin >> num;
    cin >> ch1 >> ch2 >> ch3;
	
}


```



ch=cin.get();

```c++
//函数
cin.get();
```

```c++
cout<<"\a";
```

```c++
string str;//新类型str
```

```c++
//打印整齐
setw()//限定宽度
int main ()
{
    cout << left;
    cout << setfill('*');
    cout << setw(3) << sttack1<<
            setw(3) << sttack2<<  
}
```

# 输入输出

```c++
dec            十进制表示（默认方式）
hex            十六进制表示
oct             八进制表示
setfill(char) 设置填充字符
setprecision(int) 设置浮点数的精度
setw(int)    设置输出域宽
endl           换行

```





# 数据类型



## bool

bool类型引入，只有0和1，不同与c语言里的零与非零

java-boolea

```c++
bool flag = true;
cout<<boolalpha;
cout<<15<16;
```

## int



## string



## double



#运算符

单目

双目



##左移运算符<<

2<<3=16=2^4

二进制

0000 0010.0000

0001 0000.0000

实现快速的倍数运算



##位运算符



###& 按位与

4 & 5

100

&

101

100->4



###按位非~

就是以二进制取反

~2



###按位异或 ^

同假异真



##运算符重载：

运算符重载就是"想法转换"，简化函数调用的方式



要区分cout中的情况，cout中叫插入运算，12 << 4 为左移运算符



增加代码可读性



同一运算符，两边参数不同，作用不同。

###特点



####1.不能重载的运算有五个

.(点运算符)

*(成员指针访问运算符)

::(域运算符)

sizeof(长度运算符)

？：(三元运算符/条件运算符)



####2.重载不能修改运算变量个数

.比如关系运算是二元运算的，重载后也必须有两个变量参数运算



####3.重载不能修改运算符的优先级

比如，"*"和"/"优先于"+" 和 "-" ,重载后这个优先级不会被修改



####4.重载不修改运算顺序

比如，赋值运算时从右到左的，重载后不能改变



### 成员函数实现

1.第一个参数时本类对象时才能用成员函数实现。

自定义整形

```c++
class Integer
{
    private:

            int m_num;

    public:
            Integer();
            Integer(int value); 
            ~Integer();
            int GetNum();
            Integer operator+(Integer & Int);//重载
};
```

实现

```c++
Integer Integer::operator+(Integer & Int)
{
    Integer result(this->m_num+Int.m_num);
    return result;
}
```

使用

```c++
    Integer Int1(123);
    Integer Int2(321);

    Integer Int3 = Int1 + Int2;

    cout << "Int1 + Int2 =" << Int3.GetNum() << endl;
```



### 友元函数实现

声明

```c++
 friend const Integer operator+(int value,const Integer & Int);            非成员函数不能用const修饰
```

定义

```c++
const Integer operator+(int value ,const Integer & Int)
{
    return Integer(value + Int.m_num);
}
定义无需作用域运算符，可以访问对象私有成员
```

###友元成员怎么选择

成员函数：

1.c++规定

赋值运算符=

数组下标运算符[]

函数调用运算符()

成员访问运算符->

必须声明为类的成员函数



2.一元运算符和复合赋值运算符重载时，一般声明类的成员函数

友元函数

1.流运算符<<,>>、类型转换运算符不能定义为类的成员函数，只能为友元函数



2.二元运算符在运算符重载时，一般声明为友元函数

```c++
注意
1.对于多运算符来说，可以选择使用成员函数或非成员函数来实现运算符重载，一般来说，非成员函数应该是友元函数，这样才可以访问对象的私有数据。
2.在定义运算符时，必须选择一种格式，而不能同时运用两种格式，否则，将被视为二义性错误，导致编译错误
3.对于某些运算符来说，成员函数是唯一合法的解释，但在其他情况下，这两种格式没有太大区别，有时 ，根据类的设计，使用非成员函数版本可能较好(尤其是为类定义类型转换时)
```

3.重载流运算符返回的就是cout的引用，定义的形参其实就是cout





### 重载赋值运算符

重载赋值运算符时，最好返回*this,节省内存，提高效率

自我赋值，不要做任何事：

```c++
return *this
```

证同测试

```c++
if(this == &class) return *this;
```

当有指针成员时为保证新对象完全独立，使用深复制

```c++
class Mystring
{
    private:
        char * m_String;
        int m_StrLen;

    public:
        Mystring();

        Mystring(const char * str);

        Mystring(const Mystring & str);

        ~Mystring();
        const Mystring & operator=(const Mystring & str);
        friend ostream & operator << (ostream & out ,const Mystring & str); 
        friend istream & operator >> (istream & out ,const Mystring & str); 

    protected:

};
```

```c++
const Mystring & Mystring::operator=(const Mystring & str)
{
    if(this == &str)  return *this;
    delete m_String;
    this->m_StrLen = str.m_StrLen;
    m_String = new char[this->m_StrLen+1];
    strcpy(m_String,str.m_String);
    return *this;
}
```

类成员无指针成员浅复制足矣



### 重载流运算符

声明

```c++
            friend void operator<<(ostream & out ,const Integer & Int);            
            friend const istream & operator>>(istream & in ,Integer & Int); 
```

返回值看情况



定义

```c++
void operator<<(ostream & out ,const Integer & Int)
{
    out << "值为:" << Int.m_num;
}

const istream & operator>>(istream & in , Integer & Int)
{
    in >> Int.m_num;
    Int.m_num += 1; 
    return in;
}
```

可控制对象的打印输入格式



调用

```c++
    Integer Int(856);
    cin >> Int;
    cout << Int;
```



同函数基本类似，参数，返回值，中间过程；

###重载++

#### 前置++



#### 后置++

这里我们就用到一个叫做哑元的东西，哑元就是只有类型没有名称的参数，它用来区别不同的函数，比如这里的前++和后++。

现在我们可以用这个哑元来重载后++。



##长度运算符

sizeof()

单位字节



##运算符的优先级

单目一般最高~ ++ -- sizeof ！

!

&&

||

三元运算符

？ ： ……参与运算的数目为三个

% 余数与被除数符号一致

= 右目预算

```c++
double num1 = (int)num2 / (int)num3;
```



# 对象静态数据

# ostream类

ostream在保护区所以只能调用指针或引用



#面向对象、面向过程

###面向过程：

首先考虑遵循的步骤，然后考虑如何表示这些数据。

过程性编程：编译阶段决策，考虑要遵循步骤，然后考虑如何表示这些数据

###面向对象：

一种管理源代码的方式

编程 ：模式现实 ->数据类型变量的支持

数据类型->规定变量所占空间大小 >>总统

OPP程序员首先考虑数据，不仅要考虑如何表示这些数据，还要考虑如何使用数据

强调运行阶段进行决策

由四个部分组成：

抽象

封装

继承

多态



## 何为面向对象

object oriented programming

所谓面向对象就是基于对象概念，以对象和继承为构造机制，来认识，理解，刻画客观世界和设计，构建相应的软件系统(模拟现实)。



1.对象是由数据和容许的操作(方法，函数)组成的封装体，与客观实体有直接对应关系

2.面向对象不是语言特性，而是编程思想



举个例子

斗地主--面向过程

首先考虑遵循的步骤，然后考虑如何表示这些数据。

过程性编程：编译阶段决策，考虑要遵循步骤，然后考虑如何表示这些数据

```c++
        void 开始游戏();
        void 洗牌();
        void 发牌();
        void 显示手牌();
        void 出牌();
        void 判断牌面();
        void 下家出牌();
```



斗地主--面向对象

OPP程序员首先考虑数据，不仅要考虑如何表示这些数据，还要考虑如何使用数据

强调运行阶段进行决策

```c++
1.游戏参与者--行为模式相同的玩家对象，相同的属性和行为。

2.进行游戏的场景--牌桌对象：负责显示游戏界面及内容。

3.游戏规则系统--裁判对象负责判定牌面、输赢等。

```



##抽象和类：

抽象：从具体事物抽取共同的本质特征

处理复杂问题：简化和抽象



### C++中的类

1.类是一种将抽象转换为用户定义类型的工具

2.将数据表示和操纵数据的方法组合成一个整体

3.类的实例称为对象

4.类中的变量和函数称为成员



例子：

地主类：

成员变量：名称、积分、手牌。

成员方法：摸牌、出牌、查看积分



### 类的声明使用

####class

 默认成员为私有(private)

```c++
class 类名{};                         
```



#### struct

默认成员为公有的(public)

```c++
struct 类名{};
```



#### 访问修饰符

public:自己，派生类 ，以及外部都可以访问。

private:只能自己访问，派生类及外部都无法访问

protected:自己和派生类可以访问，外部无法访问。



修饰成员：

将修饰关键字放置在类定义的打括号中，添加冒号：

```c++
class NAME
{
	public:
	
	private:
	
	pro
}
```



### 类的成员函数

####.hpp中定义

.hpp文件一般包含实现的内敛函数，通常用于模板类这种声明与实现共存的情况。

建议：只要不是纯模板，一律使用.h作为头文件后缀，使用.cpp文件作为函数的实现文件   

```c++
#include <iostream>
using namespace std;
class Landowener1
{

    private:
            string  _name;
            long int _score;
            char _cards[20];

    public:
        void GetScore(long int score)
        {
            if (score < 0)
            _score = 0;
            else
            _score = score;
        }

        void SetName(string name)
        {
            _name = name;
        }

        string ShowName()
        {
            return _name;
        }

        long int ShowScore()
        {
            return _score;
        }

};
```

​                         

####.h中定义

```c++
#include <iostream>
using namespace std;
class Landowener
{

    private:
            string _name;
            long int _score;
            char _cards[20];

    public:
            void SetName(string);
            string ShowName();

            void GetScore(long int);
            long int ShowScore();

            Landowener();
            virtual ~Landowener();
};
```

::作用域解析  运算符

```c++
#include "Landowener.h"
void Landowener::GetScore(long int score)//::作用域解析  运算符
{
    if (score < 0)
    _score = 0;
    else
    _score = score;
}

void Landowener::SetName(string name)
{
    _name = name;
}

string Landowener::ShowName()
{
    return _name;
}

long int Landowener::ShowScore()
{
    return _score;
}

```



####实体完整性

数据隐藏



## 构造函数

###特点

以类名为函数名

无返回值

### 顺序

1.虚基类

2.基类



###作用

初始化对象数据成员

类对象被创建时，编译器为对象分配内存空间并自动调用构造函数以完成成员的初始化

### 成员列表初始化

必须用初始化的情况

1.成员引用

2.成员类

3.父类

4.const常量

###无参构造

1.如果创建的类中未书写任何构造函数，系统会自动生成默认的无参构造函数(函数为空，什么都不做)

2.如果书写构造函数，系统就不会再自动生成默认构造；如果希望有这样一个无参构造函数，需要自己显示的书写出来。

声明

```C++
	Student();
```

定义

```c++
Student::Student()
{
    SetDes("");
    SetName("");
}
```

调用

```c++
Student stu1;
```

```c++
Student ptr_stu = new stu();
```



###一般构造

构造常用函数重载

声明

```c++
        Student();
        Student(string Name);
        Student(string Name,string Des);
```

定义

```c++
Student::Student()
{
    SetDes("这个人很懒什么都没留下");
    SetName("默认地主");
    cout << "默认构造" << endl;
}

Student::Student(string name) : m_name(name)
{
    SetDes("这个人很懒什么都没留下");
    cout << "设置了名字" << endl;
}

Student::Student(string name,string des) : m_name(name),m_des(des)//初始化参数列表
{
    cout << "信息已保存" << endl;
}
```

调用

```c++
    Student stu("杰克马","社会");
    Student stu1;
    Student stu2("小马哥");
    
    Student * ptr_stu  = new Student();
    Student * ptr_stu1 = new Student("小马哥2");
    Student * ptr_stu2 = new Student("杰克马2","社会");
```

###转换构造

仅有一个参数的构造；

可用等号赋值；

```c++
Date(year);
```

```c++
Date date = 9;
```



###拷贝构造

### 形参为对象

默认复制构造

####默认定义

默认为浅复制

对于简单的类，默认拷贝构造是足够的



####显式定义：

当类拥有其他资源，如动态分配的内存、打开的文件、指向其他数据的指针、网络连接、等，默认拷贝构造不能拷贝这些资源，必须显示定义拷贝构造函数、以完整的拷贝对象的所有数据。

```c++
Mystring::Mystring(const Mystring & str)
{
    m_StrLen = strlen(str.m_String);
    m_String = new char[m_StrLen+1];
    strcpy(m_String,str.m_String);
}
```

调用

```c++
Mystring str2(str1);
```

无指针时，无需定义也可

```c++
Mystring str2(str1);
```



#### 何时自动调用

1.当类的对象被初始化为同一类的另一个对象时。

2.当对象被作为参数传递给一个函数时。

3.当函数返回一个对象时。



## 析构函数

###特点

对象过期时自动调用的特殊成员函数

析构函数一般用来完成清理工作

析构函数的名称是在类名前加上~

析构函数只有一个，且不能有参数

析构函数用来释放对象使用的资源，并销毁对象的static数据成员

无论何时一个对象被销毁，都会自动调用其析构函数(隐式析构)

### 声明

```c++
~Student();
~className();
```

### 定义

```c++
Student::~Student()
{
    delete ptr_name;……
    cout << m_name << "被释放了" << endl;
}
```



###调用

```c++
Student stu;
//栈区自动调用释放
```

```C++
delete ptr_stu;
//堆区的用delete
```



## this 指针

每个成员函数(包括构造和析构)都有一个this 指针

this指针指向调用对象，即通过this关键字可以访问当前对象成员

this指针为类型为类类型*const,为右值

this指针本身不占用大小，它并不是对象的一部分，因此不影响sizeof的结果

this的作用域在类成员函数内部

this指针是在类成员函数的第一个默认隐含参数，编译器自动维护传递，类编写者不能显示传递

只有在类的非静态成员函数中才可以使this指针，其他任何函数都不可以



```c++
this 指针并非对象的指针，是内部的一个指针
```



### c语言原理

```c++
void AddScore(Student * const stu )
```



```c++
this->函数名;
```

```c++
this->成员名;
```

```c++
void Student::AddScore(float score)
{
	this->score[this->scoreCount - 1] = score
	float newscore = new float[2];
	memcpy(newScore,scores,sizeof(float)*scorecount);
	delete scores;
	this->scores = newscore;
	
}
```

### 返回当前对象的引用





### 对象之间的赋值



## 继承与派生

在c++中，代码重用是通过 "继承(inheritance)" 机制实现的。

```java
所谓继承就是在一个已存在的类的基础上，再建立一个新类

从已有类派生出新的类，派生类就继承了原有类的特征，包括成员和方法
```



通过继承可以完成下面的一些功能

```javascript
可以在已有类的基础上添加新的功能

可以给类添加数据成员，

可以修改类方法的行为。
```



继承机制只需提供新特性，甚至不需要访问源码就可以派生出类

```python
即，如果购买的类库只提供了类方法的头文件和编译后的代码，仍可以使用库中的类派生出新的类，而且可以不公开实现的情况下将自己的类分发给其他人，同时允许他们在类中添加新特性。
```



优点：

```php
基类定义公共内容，方便统一修改

重定义基类的成员函数

添加新类，新成员，方便。
```



```basic
派生类对象存储了基类的数据成员

即，派生类继承了基类的实现

派生类对象可以使用基类的非私有函数

即，派生类继承类基类的接口

派生类需要自己的构造函数

派生类可以根据需要添加额外的数据成员和函数
```



1.派生类的构造函数后于其基类构造函数调用，但是析构函数先与基类析构函数调用

2.派生类的成员访问有三种方式：公有访问 ，私有访问，保护访问。

3.类的继承和类的组合是面向对象编程的核心





### 继承方式



```basic
私有继承：私有继承是一种实现技术，所以在软件的设计层面没有意义，只有在软件的实现层面，能够使私有继承向下隐藏细节
```

```basic
私有继承可以实现 has - a 关系，但大多数程序员倾向于使用包含实现has - a ,一是容易理解，二是继承特别是多继承会引起很多问题。
```



使用：

```basic
全部继承，不封装基类，那么用公有继承

全部继承，完全封装基类，那么使用私有继承

全部继承，有选择封装基类，那么使用保护继承

```



这三种选择是程序员在开发中运用面向对象思想的重要体现：

```CQL
需要封装那些成员变量，和成员函数?

需要把那些成员作为借口被调用?
```



```
派生类对象可以使用基类的非私有成员函数。

基类指针可以在不进行显式类型转换的情况下指向派生类对象

可以将派生对象赋值给基类对象，程序将使用隐式重载赋值运算符



基类指针或引用只能调用基类函数并不能调用派生类函数

不可以将基类对象地址赋给派生类引用和对象，即不能够做逆操作

```



###类的组合

在一个类中有另外一个类的对象作为数据成员，这种方式叫做类的组合形式。

通过继承建立了派生类与基类的关系，他是一种 is-a "是" 关系。

比如：狗 是 动物



类的组合关系，它们之间不是 "是" 的关系 而是 " 有 " 的关系

不如：学生有书包



继承是纵向的，组合是横向的



```
构造函数该如何去用？

在何时初始化何成员？
```



### 继承构造顺序

1.基类构造

2.成员类构造

3.完成派生初始化

从上到下调用，先调用父类，再调用派生类

```c++
例：
Galon::Galon(string name) : Hero(Name)
{

}

若不初始化调用Hero(Name)
    
那么
Galon::Galon() ：调用默认Hero(),默认调用Warrior()
{
    
}
```

### 继承析构函数顺序

同构造相反

1.派生类

2.成员类

3.基类

## 多态

例：演员-表演方法-》不同效果，同一类，同一方法，不同效果。



一种语言不支持多态不能称为面向对象语言，即使其支持类概念，但也只能称为使用基于对象的语言。如vb



gamecore:游戏引擎核心

万能接口，多态转换输出



实现多态的地方



vector<*>，vector装类的指针比较合适，遍历方法，for( auto it ： vecName)



可升级可维护



静态多态：编译时多态：依赖函数重载

动态多态：运行时多态：依赖虚函数

虚函数：virtual

函数重写：viride

重写后将以重载的形式重现

```c++
	Hero.Move();
	Warrior.MOve();
	Galon.Move();//实际调用
```



子类重写：

基类中的函数和子类不一样:



### 探究虚函数标的内存地址



![image-20200314213645539](C:\Users\BUPEI\AppData\Roaming\Typora\typora-user-images\image-20200314213645539.png)

三级指针：

对象->虚拟函数列表指针->虚拟函数地址(也是一个指针)

```c++
	int * ObjPtr (int *)&obj;
    int * visListAddress = (int *) * (ObjPtr + 0);
    int * List1Address = (int * ) * (visListAddress + 0);
    int * list2Address = (int *) * (visLIstAddress + 2);
```

​         ![img](file:///C:/Users/BUPEI/AppData/Local/Temp/msohtmlclip1/01/clip_image001.png) 

##虚析构函数

如果不加virsual派是类对象在释放时只会调用一个析构函数

## 绑定

###编译时多态



###运行时多态







## 抽象类

抽象类不可实体化，只能被继承：不可用抽象类定义一个对象



可以定义抽象类指针引用。



只要有一个纯虚函数就可标志抽象类



纯虚函数一般没有函数体：可以实现抽象基类的默认实现



纯虚函数必须有派生类来实现其，否则链接错误，在基类无法调用

###虚函数

父类有虚函数则子类默认为虚函数。



## 虚基类





## 多重继承

一个类继承多个父类。





QT：一种用于C/C++开发的应用程序开发框架，既可以开发GUI，又可以开发控制台应用。

MFC

## 类的成员变量







# const修饰

c++中是编译时常量

c中是普通常量



## 修饰普通变量

```c++
	const int num1 = 1;
	int const num2 = 2;
	
	const float num1 = 1;
	float const num2 = 1;
```

变量为常量，只读，不可修改。

## 修饰指针变量

1.

```c++
const int * ptr_int = &num;
int const * ptr_int = &num;

ptr_int = & num2; //合法
*ptr_int = 321 ; //不合法
```

指针所指数据为常量，不可通过*修改所指数据

指针本身是是变量

2.

```c++
int * const ptr_num1 = &num2;

ptr_num1 = &num;//不合法
*ptr_num1 = 32;//合法
```

定义指针常量，指针值不可修改

可通过寻址符修改所指数据

3.

```c++
const int * const ptr_num = num;
```

指针常量，指向常量

只可以读



## 修饰函数

不能修改任何成员

不能调用非const成员函数

```c++

void functioname() const;

void functioname() const
{

}
```



## 修饰引用

### 引用为返回值应为const

```c++
int & test2(int & num1 ,int & num2)
{
    num1++;
    num2++;
    return num1;
}
```

```c++
    int & ref_2 = test2(num1,num2);
    cout << ref_2 << '\t' << num1 << endl;
    
    test2(num1,num2) = 250;
    cout << ref_2 << '\t' << num1 << endl;
```

结果test2()改变了ref_2的值；



###引用为参数

修饰引用时，不能修改引用对象的任何成员

```c++
void test(const class & someone)
{
	someone.buy();//只能调用const成员函数
}
```

好处：

1.保护传递参数

2.无需生成副本，节省内存,提高效率

```c++
void test(const class & someone);
```





## 修饰返回值

1.说明函数值为又值

2.长用于指针，引用。







#二进制补码

负数的补码 = {原码符号位不变} + {数值位按位取反后+1}正数反码补码原码相同，为什么呢？规定的！因为计算机通常只有一个加法器，做减法器太麻烦。所以就将减法连着减数作为负数来处理，就只需要加了。但是正数和一个负数在计算机这样一个用二进制表示数的环境中如何进行加法计算呢？于是我们可以忽略正数的变化，主要是要处理负数变成一种二进制表示让它能和正数相加。比如在计算机中1的二进制表示0001.-1的二进制表示1111（这是补码反码引进后变化后的）0001+0111=10000但是显然这里的位数是4位的所以只会出现0000，也就是0，就完成了1-1=0这个计算。





#数组array

数组中数据必须是相同数据类型

c++中数组长度可谓变量

```c++
int N = 100；
int a[N] ;
```

部分初始化默认初始化为0

字符数组部分初始化

数组大小一旦确定了，就无法更改了

数组长度

```c++
for(int i=0;i<sizeof(nums)/sizeof(datatype);i++)
```

c++写法

```c++
int nums[]{3,3,4,2,32,};
```

maxIndex:下标

### 数组排序

#### 冒泡排序

？部分初始化结果

```c++
//从左至右
int main ()
{
	int tem;
    
    int nums[20]{1,2,3,4,-2};
    int numsleth = sizeof(nums)/sizeof(int);
    for(int i=0;i<numsleth-1;i++)    	//外层循环控制比较的轮数lenthof(arry)-1;
    {
        for (int j=numsleth-1;j>i;j--)	//内层循环控制比较次数；
        {
            if(nums[j]<nums[j-1])	    //判断后交换
            {
                tem = nums[j];
                nums[j] = nums[j-1];
                nums[j-1] = tem;
            }
        }
    }
    
        
}
```



```c++
//从右到左
int main ()
{
	int tem;
	int nums[]{1,24,54,65};
	int numsLen=sizeof(nums)/sizeof(int);   		 
    for (int i=0;i<numsLen-1;i++)		//控制循环轮数
    {
        for (int j=0;j<numsLen-1-i;j++)	//控制比较次数
        {
            
            if(nums[j]<nums[j+1])	   //判断后交换
            {
             tem=nums[j];
			nums[j]=nums[j+1];
             nums[j+1]=tem;
            }
        }
    }
}
```



#### 选择排序

```c++
int main ()
{
	int nums[]{12,34,354,4,454,7657};
    int numsLen = sizeof(nums)/sizeof(int);
    int tem;
    int min = nums [0];                //假设最小值为第一个元素.擂台变量
    int minIndex = 0;                 //最小值的初始下标设置为0；
    for (int i = 0;i < numsLen-1;i++)//外层循环控制比较的次数，确定排位的次序数i
    {
        min = nums [i];            //循环内部初始化比较擂台数
        minIndex = i;
		for (int j = i + 1; j < numsLen; j++)//确认次序数位置
        {
			if(nums[i] > nums[j])
            {
			   min = nums[j];
                minIndex = j;
            }

        }
            
        if(minIndex > i)			//交换得出次序数
        {
             tem = nums[i];
             nums[i] = min;
          	 nums[minIndex] = tem;
        }
    }
        
        for (int i=0;i<numsLen;i++)
    {
        cout << nums[i] << '\t' << endl;
    }
    return 0;
}
```



#### 逆序

```c++
for (int i = 0; i < arrylen/2 ; i++)  
{
	tem = arry[i];
	arry[i] = arry[arrylen-i];
	arry[arrylen-i] = tem;
}
```



####快排





#### 插入排序





##数组的删除

1，找到删除数字的位置

```c++
   for (int i = 0; i<numsLen; i++)
    {
        if(nums[i] == DeleteData)
        {
            DeleteIndex = i;
            break;
        }
    }
```

2.从找到的下标开始，后面一个元素赋值给前面一个元素。

```c++
        for (int i=DeleteIndex; i<numsLen-1; i++)
        {
            nums[i] = nums[i+1];
        }
```

3.长度减一





##插入

1，找到**第一个**比插入数字大的位置

```c++
 for (int i=0;i<numsLen;i++)
    {
        if(nums[i]<=insertDigit)
        {
            insertIndex = i;
            break;
        }
    }
```



**2.从最后一个元素开始**，将数字复制到后面一个元素中。

```c++
        for(int i=numsLen;i>insertIndex;i--)
        {
            nums[i]=nums[i-1];
        }
```

3.将要插入的数字赋值给下标为insertIndex的元素

```c++
nums[insertIndex] = insertDigit;
```

4.总实际长度减一

```c++
numsLen++;
```





##二维数组

  	刘	关	张

语	 1	 2	 3

数	 4	 5	 6

英	 7	 8     9

  	语	数	英

刘	 1	 4	 7		

关	 2	 5	 8

张	 3	 6	 9

以人

```c++
                for (int i = 0; i < col; i++)
                {
                    for (int j = 0; j < row; j++)
                    {
                        cout << student[i] << object[j] << "为:" << score[j][i]<<endl;
                    }
                }
```

以科

```c++
                for (int i = 0; i < row; i++)
                {
                    for (int j = 0; j < col; j++)
                    {
                        cout << student[j] << object[i] << "为:" << score[i][j]<<endl;
                    }
                }
```

行：row

列：column



#容器vector

vector 是一个快速的动态分配内存的数组

是一个模板类

动态数组，可以在运行阶段设置长度

具有数组的快速索引方式

可以插入删除元素

![image-20200221200243504](C:\Users\BUPEI\AppData\Roaming\Typora\typora-user-images\image-20200221200243504.png)

##建议使用场景

1.开始就知道元素的数量

2.对数据的索引和随机访问频繁

3.插入和删除大多数在尾端



##定义和初始化

```c++
#include <algorithm>
#include <vector>
```

```c++
vector<double>vec1;//不给大小
vector<int>vec2(5);//给大小
vector<int>vec3(20,998);//给大小和初始化
vector<double> vecDouble = {32,343,54};
```



``` c++
//向数组中插入数字
vecDouble.push_back(110.8);//在数组的尾部插入一个数字>换一个大容器过程；
//遍历1
for(int i = 0; i < vecDouble.size();i++)
{
	cout<<vecDouble[i]<< endl;
}
//遍历2通用方法，使用迭代器，iterator >变量>用于循环的变量
//以下是迭代器基本用法
vector<double>::iterator it;	//得到迭代器对象-实际上是一个指针对象
//从第一个元素开始迭代
for (it = vecDouble.begin();it != vecDouble.end(); ++it)
{
	cout << *it << endl;
}

//排序
sort(vecDouble.begin(),vecDouble.end());
//逆序
reverse(vecDouble.begin(),vecDouble.end());
//清空
clear();
//判断是否为空
empty()
//插入
insert(pos,data);


```

```c++
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;
int main ()
{
    //定义
    vector<string> vecString = {"刘备","关羽","张飞"};
    //获取迭代对象
    vector<string> ::iterator itString;
    //插入
    vecString.push_back("阿斗");
    //输入
    cin >> vecString[0];
    //排序
    sort(vecString.begin(),vecString.end());
    //输出
    for (itString = vecString.begin(); itString != vecString.end() ; ++itString)
    cout << *itString << endl;
    return 0;
}
```



## 相关函数

```c++
//查询函数，返回迭代器(指针),没查到返回 尾指针
find(vecSurplusCrads.begin(),vecSurplusCrads.end(),cardNum);
```

遍历容器区间

```c++
//迭代器法
for(vector<int>::const_iterator it = Cards.begin() ; it != Cards.end() ; ++it)    
cout << *it << endl;

//区间法
for(auto card: Cards)
cout << card <<",";

//copy函数，belong to al
copy(Cards.cbegin(),Cards.cend(),ostream_iterator<int>(cout, ", "));

```

```c++
//删除函数，返回值  下一个空间指针
deletecards.erase(iter);

//删除区间
deletecards.erase(begin,end);
```



#指针 pointer



## 基本概念

指针是一个值为内存地址的变量（或数据对象）



变量名自取重复，访问复杂，CPU访问时直接利用该空间地址



形式：十六进制数八位



当一个指针变量存储一个变量的地址，那么称该指针变量指向该变量。



*ptr_num, *取值符



&num, &取址符



test:指针与字符串首地址的冲突。

```c++
char ch = 'a';

char * ptr_ch = &ch;//->char * str = {"hhh"};

cout << ptr_ch << * ptr_ch <<;
```

#### 指针的定义

指针类型丰富，定义类型时以‘*’为标志，以后坠类型判断



二维数组指针：int (*ptr_arrayname)[LEN];



三维数组指针：int (*ptr_arrayname)[ROW] [LEN];



函数指针：void (*ptr_funtioname)(int ,int);//一个返回类型为空，参数为两个整形的函数指针





## 指针初始化

```c++
int * ptr1 = nullptr;//等价于 int *ptr1 = 0;
int * ptr1 = 0;
int * ptr2 = NULL ;//NULL用define 定义的0于cstdlib中
nullptr 特殊的字面值；可以转换成任意类型指针；

```

```c++
std::nullptr;
```



##void * 指针

```c++
    double num = 3.3;
    double * ptr_num1 = &num;

    void   * ptr_num2 = &num;
    
    cout << boolalpha;
    cout <<(ptr_num1 == ptr_num2) << endl;

    double * ptr_num3 = (double *)ptr_num2;
    cout << ptr_num3;
```

###void * 类型指针一般用来：

同其他指针比较



作为函数的输入输出



赋值给另一指针



**由于无法通过void指针修改内容，传参相对安全**



## 指针的算数运算

++，--,指针的平移

### 观察指针分配空间是否为连续

```c++
    double score1[]{34,54,343,2432,4};
    double score3[]{34,54,343,2432,4};
    double score4[]{34,54,343,2432,4};
    double score5[]{34,54,343,2432,4};
    double score6[]{34,54,343,2432,4};
    double * ptr_score = score6;

    cout << *(ptr_score+15);
```

```c++
cout <<*++score;//wrong
cout <<*++ptr_score;//true
```



###test:移动大小于所指类型相关

```c++
    double * ptr_double;
    int * ptr_int;

    cout<<ptr_double++<< '\t' <<ptr_double++<<endl;

    cout<<ptr_int++   << '\t' << ptr_int++<<endl;
	0x10     0x18
	0xa19b0  0xa19b4
```

以字节为基本指向

16^8 = Byte;

## 函数指针

函数也有地址

函数的地址是存储在机器语言代码的内存开始地址

代码中为函数名为地址常量

好处：可以在不同的时间使用不同函数

可以将函数作为参数传递

### 定义

1.

```c++
	int (*ptr_fun) (int ,int )
```

2.

```c++
	auto ptr_fun = ini_function;
```

3.

```c++
	typedef int (*PTR_FUN)(int ,int);
	PTR_FUN ptr_fun;
```



### 赋值

代码中为函数名为地址常量

```c++
	int mul (int a,int b);

	int sum (int a,int b);

	int (*ptr_math)(int ,int );// auto ptr_math = add;
	if(?)
        ptr_math = mul;                                    
	else
        ptr_math = mul;
	cout << (*ptr_math)(a ,b);

	
```





## 指针函数

### 返回函数指针

####定义格式

```c++
返回函数的返回类型 (* 函数名(形式参数)) (返回函数的形参类型)

void (*FuncName(unConfirm parameter))(unConfirm unConfirm)

double (*Kind_Calc(char symble_k))(double ,double )
```



```c++
/**返回 函数指针 的函数*/
double (*Kind_Calc(char symble_k))(double ,double )
{
    
    switch(symble_k)
    {
        case '+':
            return add;
        case '-':
            return sub;
        case '*':
            return mul;
        case '/':
            return divi;
        default:
            return add;
    }

}
```





## 指针数组







## 指针与vector



#引用

**reference**

1.非对象，为对象起的另一个别名，引用更接近const 指针，关联后效忠于唯一变量。

2.引用必须初始化

3.指向常量的引用

```c++
const double & ref = 100;
```

4.**无需测试其有效性，比指针高效**绕开测试，以别名自居。

5.引用对指针进行了简单的封装，底层仍然是指针，获取引用地址时，编译器会进行内部转换

6.同一个对象可以有多个引用

```c++
int int_value = 1025;
int& refValue = int_value;
const double& ref = 100;


int num = 108;
int& rel_num = num ;
rel_num = 118;
cout << &num <<'\t'<< &rel_num << endl;

//等价于
int num= 108;
int * rel_num = &num;
*rel_num = 118;
cout << &num << '\t' << rel_num <<endl;
```

```c++
	void change(int ,int );
	
	void change(int * , int *);
	
	void change(int & ,int & );
```

1.简便书写代码

2.直接传递某个对象，而不是副本

## 引用做参数

1.能够修改调用函数中的的数据对象

2.数据对象较大时传递引用可以提高程序运行效率

```c++
void change(int & num1,int & num2)
{
    int temp;
    temp = num1;
    num1 = num2;
    num2 = temp;
}

```

### 函数不需修改传递的参数

1.如果数据对象很小，建议按值传递。

2.传递数组时只能使用指针，并使用const关键字。

3.较大的对象则使用const指针或引用，以提高程序的效率



### 函数需要修改传递的参数

1.数据对象是基本类型或结构时，可以使用指针或引用（基本类型建议使用指针）。

2.数据对象时数组时只能使用指针

3.数据对象时类对象时，要求使用引用



## 返回值引用

### 缺少返回值

```c++
int & sum(int & num1,int & num2)
{
	num1++;
    num2++;
    
}
```

结果为：返回最近一个引用

### 返回值应为const值

```c++
int & test2(int & num1 ,int & num2)
{
    num1++;
    num2++;
    return num1;
}
```

```c++

    int & ref_2 = test2(num1,num2);
    cout << ref_2 << '\t' << num1 << endl;
    
    test2(num1,num2) = 250;
    cout << ref_2 << '\t' << num1 << endl;
```

结果test2()改变了ref_2的值；



# 动态内存分配

##指针创建二维数组

```c++
    /**一维数组*/
    int * oneD = new int[10];

    /**二维数组*/
    int (*twoD)[23] = new int[13][23]; //降维

    *(*(twoD+2) + 3) = 2020;

    cout << twoD[2][3] << endl; 
```

```java
0 |	1	2	3	4	5	6	7	8	
1 |	*	*	*	*	*	*	*	*	
2 |	* >	*	*	*	*	*	*	*
3	*	*	*	*	*	*	*	*
4	*	*	*	*	*	*	*	*
5	*	*	*	*	*	*	*	*
```



## 使用new获得内存

指针的真正用武之地：在运行阶段分配未命名的内存以存储值

在此情况下，只能用指针来访问内存

```c++
int * ptr_int = new int;
```

```c++
    int * ptr_int = new int;
    *ptr_int = 10;
    cout << *ptr_int << '\t' << ptr_int << endl;

    double * ptr_double = new double;
    *ptr_double = 20.0f;
    cout << *ptr_double << '\t' << ptr_double << endl;

    int * ptr_intArray = new int[3];
    //int * ptr_intArray2 = new int[3] = {1,2,3}; wrong
    for (int i=0 ; i<3; i++)
    *(ptr_intArray+i) = i;
    
    for (int i=0 ; i<3; i++)
    cout << *(ptr_intArray+i) <<'\t';
    cout << ptr_intArray << '\n' <<endl;
    
    delete ptr_int;
    delete ptr_double;
    delete ptr_intArray;

    cout << *ptr_int << '\t' << ptr_int << endl;
    cout << *ptr_double << '\t' << ptr_double << endl;
    
    for (int i=0 ; i<3; i++)
    cout << *(ptr_intArray+i) << '\t';
    cout << ptr_intArray <<endl;
```



```c
10      0xfa1ea0
20      0xfa1ee0
0       1       2       0xfa1a70

16390768        0xfa1ea0
-2.65698e+303   0xfa1ee0
16400384        0       16391840        0xfa1a70
```



##编译时

```c++
int num[3];
```

编译后即获得内存



##运行时

```c++
int *ptr_num = new int[3] ;
```

运行时才分配空间



## 使用delete释放

同new配对使用

不要释放已经释放的内存

不能释放声明变量分配的内存

int a;

delete &a;

```c++
int * intArray = new int[10];
delete[] intArray;
```

??二维数组

```c++
int* ptr_int = new int;
short * ptr_short = new short[500];

delet ptr_int;
delet[] ptr_short
```



##程序的内存分配

###栈区:(stack)

访问速度快

由编译器自动分配释放发，一般存放函数的参数值，局部变量的值等

操作方式类似数据结构中的栈-先进后出

栈内存的优势是存取速度比较快(仅次于寄存器)，缺点是存在栈中的数据大小与生存期必须是确定的，缺乏灵活性。

###？先进后出



###堆区:(heap)

一般由程序员分配释放，若程序不释放，程序结束时可能由操作系统回收

注：与数据结构中的堆是不同的两个概念，同链表的分配类似



###全局区：

也称静态区（staic)

存储全局变量和静态变量

程序结束由系统释放



###文字常量区：

常量字符串放在此处

程序结束由系统释放



###代码区：

存放函数体的二进制代码





# 函数

## 内置函数

STL 和 Boost C++

![image-20200215145435636](C:\Users\BUPEI\AppData\Roaming\Typora\typora-user-images\image-20200215145435636.png)

####memset 函数





## 自定义函数

###函数三要素

返回值类型：决定函数类型

函数名：                          

参数列表：接口

####函数原型：

```c++
int sum (int ,int );
```

####函数调用

```c++
	 int main()
	 {
		sum();
	 }
```

####函数定义

```c++
	int sum(int a,int b)
    {
        return a+b;
    }
```



## 参数

### 参数为引用

起到操作同一内存空间作用

```c++
	 sum (int & num)
	{
		num++;
	}
	
	int main ()
	{
		int num = 1;
		sum(num);
		cout << num;
		retrun 0;
    }
```







### 参数为数组

实际为指针

传递指针同时，最好传入数组长度

#### 二维数组

声明

```c++
	void show(double [][], int len);

	void show(double (*)[3],int len);
```

定义

```c++
	void show(double array[][], int len)
	
	void show(double (*array)[3], int len)
```



### 只读保护

```c++
	void output(const int values[], int size)
        
	void output(const int * values, int size)
```

传入一个指针常量，无法通过寻址符更改数组



### 参数为函数指针

当有许多同类型的函数时可以简化操作

1.判断使用函数类型后，统一交付一个函数处理。

```c++
double Calc_result(double (*s)(double ,double ),double a,double b)
{
    return (*s)(a,b);
}
```



### 默认参数

1.定义与声明中 只能一方定义

```c++
void sample (int = 10 )；

void sample (int num = 10)
{
    ……；
}
```

2.对于带参数列表的函数，必须从右向左默认

```c++
	int add(int , int = 1);
	add(3);	

	int Calc(int ,char = + ,int =6);
	Calc(3);
```



## 返回值

### 函数指针

```c++
/**返回 函数指针 的函数*/
double (*Kind_Calc(char symble_k))(double ,double )
{
    
    switch(symble_k)
    {
        case '+':
            return add;
        case '-':
            return sub;
        case '*':
            return mul;
        case '/':
            return divi;
        default:
            return add;
    }

}
```



### 引用

1.不要返回局部变量的引用

 局部变量内存被回收，回收后虽然不一定立即覆盖，但是会被其他变量申请时覆盖。

```c++
	int & sum ()
	{
        int num = 10;
        
        int & rel_num = num;
        
        return rel_num;
	}

	void test ()
    {
       int x = 1;
       
       int y = 3;
        
       int v = 5443;
        
       int ds = 3432;
        
       int dfd = 34;
    }

	int main ()
    {
		int & rel_num = sum();
         test();                                                                                          cout << "result = " << rel_num << endl ;
     
    }
```

2.当不返回值时

```c++
	int & test(int & num1, int & num2)
    {
		num1++;
         num2++;
         num1++;
    }

	int main ()
    {
        int num1,num2;
        
        test (num1,num2);
        
        int & rel = test(                )
    }


```

实际返回最近的引用。



### 局部对象

如果想要返回对象变量，返回对象本身



 

## 内联inline函数

1.是c++为了提高程序运行速度做的改进

2.与常规函数的区别在于被调用时的机制不同

编译器使用函数代码替换函数调用

**拿过来用，走过去用**>>>副本 与 跳转

3.适用于执行代码时间短的函数：提升速度，占用内存。

**与函数指针配合，**

```c++
inline double add(double , double );
inline double sub(double , double );
inline double mul(double , double );
inline double divi(double , double );
double Calc_result(double (*)(double ,double ),double ,double );
double (*Kind_Calc(char))(double ,double );
```



### C时代的内联

```c++
	#define N 5   //替换

	#define S(num)  num*num
	
	cout << S(num) << endl;
```



###定义

1.声明时加inline

2.在定义时加inline

```c++
	inline int S(int num);
	
	int S(int num)
	{
		return num*num;
	}
```



### 特性

编译器可能忽略长代码内联函数





## 函数重载

overloading



### 定义

1.指可以有多个同名函数

2.函数名相同，参数列表不同（数量不同，特征标不同）

```c++
	void eating(string food);

	void eating(string & food);

	error:call of overloaded is ambiguous
```

.1从编译器的角度看，eating(sting)和eating(sting&)的特征标是相同的，调用时都可以写作：eating(food);

为避免混乱，编译器把类型引用和类型本身视为同一个特征标。

.2在调用匹配函数时，不区分const和非const变量。

```c++
 特征标
    重载-编译器在编译时，根据参数列表对函数进行重命名
    重载决议
    
    void swap(int ,int ); >> swap_in_int;
    void swap(int ,float); >> swap_int_float;
```



### 例

数组排序函数

```c++
void Sort(int num[]);
void Sort(double num[]);
void Sort(float num[]);
```





##函数模板

Function Template

1.实际上是建立一个通用函数

2.函数定义时不指定具体的数据类型（使用虚拟类型代替）

3.函数被调用时编译器根据实参反推数据类型-类型的参数化



```c++
template<class T> 早期写法

template<typename unConfirm,typename unConfirm2> void change(unConfirm & ,unConfirm2 & );

template<typename unConfirm,typename unConfirm2> void change(unConfirm & a,unConfirm2 & b)
{
    
}

```

一定程度替代重载，当函数因数据类型逻辑结构不同时，重载仍然有重要意义。

当我们写底层框架时，模板应用使用较多。

```c++
//模板头与函数声明/定义永远时不可分割的整体
template<typename unConfirm> void change(unConfirm & a,unConfirm & b)
{
    unConfirm temp;
    temp = a;
    a = b;
    b = temp;
}

template<typename unConfirm> void sort(unConfirm * Array_name,int Len)
{
    for (int i = 0; i < Len ; i++)
    {
    for (int j=0; j < Len - i - 1 ; j++)
    {
        if (Array_name[j] < Array_name[j+1])
        change(Array_name[j],Array_name[j+1]);
    }
    }

}
template<typename unConfirm> void output(unConfirm * Array_name,int Len)
{
    for ( int i = 0 ;i < Len ; i++)
    cout << Array_name[i] << '\t';
    cout << endl;
}
```







## 递归

### 汉诺塔问题

hanoi

A    B     C

1.将A上n-1个盘子移到B上--借助C

2.将A上剩余的盘中移到C上--至此仅移动好了第n个

3.将B上n-1个盘中移到C上--借助A



# 命名规范

## 变量命名

全局变量 g_ 
常量 c_ 
c++类成员变量 m_ 
静态变量 s_

# 类型转换

自动转换

```c++
int a = 12;
a = 22.5 + a;
```

c语言

```c++
int a = (int)4.44;
```

c++

```c++
int a = int(2.22)
```



## 自定义类型转换

###类型转换函数

类型转换函数的作用就是将当前类类型转换为其他类型。

它只能以成员函数的形式出现，也就是只能出现在类中。



类型转换函数看起来没返回值类型，其实是隐式地指明了返回值类型

类型转换函数也没有参数，因为要将当前类的对象转换为其它类型

实际上编译器会把当前对象的地址赋值给this指针，这样在函数体内就可以操作当前对象了。

```c++
operator float() const
{
	return ...
}

```

type可以是内置类型，类类型以及由typedef定义的类型别名，任何作为函数返回类型的类型（除了void）,都是被支持的，不允许转换为数组或函数类型，可以转换为指针或引用类型

类型转换函数一般不会更改被转换的对象，所以通常被定义为const.

```c++
class dad
{
	pulic:
	dirve();
	
	protect:
	fixComputer();
}
class mum
{
	public:
	sing();
	
	private:
	jiajiao();
}
class son：public:dad,
{

}
```



# 链接库

## 静态链接库

```c++
#include "../lib.h"
#pragma comment (lib,"../lib.lib")
```

## 动态链接库

###显式调用：

```c++
#include "iostream.h"

#include "windows.h"

void main()
{
	typedef int (*ADD) (int,int);   
	ADD  fun=NULL;
	HINSTANCE hinst=NULL;//HMODULE hinst=NULL;
	hinst=LoadLibrary("Caculate.dll");
	if (hinst==NULL)
	{//没有加载成功
		MessageBox(NULL,"提示","DLL加载失败",1);
		return;
	}
	fun=(ADD)GetProcAddress(hinst,"add");
	
	if (fun==NULL)
	{	MessageBox(NULL,"提示","函数加载失败",1);
		return;
	}

    cout<<fun(5,6)<<endl;
	FreeLibrary(hinst);
    
}
```

HINSTANCE hinst=NULL;//HMODULE 

hinst=LoadLibrary("Caculate.dll");

fun=(ADD)GetProcAddress(hinst,"add");

FreeLibrary(hinst);

###隐式调用

```c++
#include "../lib.h"
#pragma comment (lib,"../lib.lib")
```





## 非MFC







## MFC







## 类



## .def文件



LIBRARY "dll"

EXPORTS:

​	ADD @1;