# 数据类型与常量变量

之前介绍，C语言有丰富的数据类型，主要有四大类：

1. 基本类型：`int`整型、`float` `double`浮点型、`char`字符型、`enmu`枚举型；
2. 构造类型：数组类型、`struct`结构体、`union`共用体；
3. 指针类型；
4. 空类型：`void`。

本讲主要讲解基本数据类型。

##常量

在程序执行过程中，值不能进行修改的量称为常量。

###整型常量

整型即整数，用关键字`int`表示。如`1`、`2`、`3`，为常量。

###浮点型常量

浮点型即小数，在程序中因为精确位数不同，有单精度与双精度之分。

- 单精度用关键字`float`表示，精确到6~7位。如`2.5f`、`3.8f`，为常量。

- 双精度用关键字`double`表示，精确到15~16位。如`7.9`、`124.9`，为常量。

###字符型常量

字符型包括0~9数字，与字母符号，用关键字`char`表示。

值得注意的是，字符的表示需要用`''`单引号引起来，方式为：`'a'`、`'0'`。中文以及一串字符，<font color=red>不能</font>用char表示，错误写法`'我'`、`'abcde'`。

###枚举

枚举即一一列举的意思。比如一周七天：星期一、星期二、星期三...

写法：

```
enum Weekday {Monday, Tuesday};

```

枚举值是常量，不能在程序中在对其进行修改。

###宏定义

也可以使用`#define`宏定义来定义常量，表示为：

```
#deinfe NUMBER 5
```

##变量

在程序运行过程中，值可以进行修改的，称为变量。变量必须有一个名字，并占用一定存储空间。如：当前时间。

###变量的定义

定义的格式为：

```
变量类型 变量名;
int a;
float b;
double c;
char d;

```

多个相同类型的变量可定义为：

```
变量类型 变量1, 变量2, 变量3;
int a, b, c;

```

###变量的命名

变量命名首先需要遵循标识符的命名规则，除此之外，为了编码规范，还需要遵循以下几点：

1. 变量名要做到见名知意，如：`int number;`；
2. 首字母小写；
3. 多个单词使用<font color=red>驼峰法</font>（即，除第一个单词外，其余首字母大小）命名：`int myFirstName;`；

<font color=red>注：不能定义重名的变量</font>

###变量的初始化与赋值

- 初始化：在定义变量时，直接给变量值。如：`int number = 5;`。
- 赋值：变量定义以后，再给变量值。

```
int number;  // 定义变量名为number的整型变量
number = 4;  // 将整型常量4赋值给number

int otherNumber = 10; // 定义一个整型常量otherNumber，并初始化为10
number = otherNumber; // 将变量otherNumber赋值给number


```
###变量作用域

变量只在当前`{}`有效。如：

```
int main() {

    int number = 4; // 当离开main函数的{}以后，number就失效了，无法继续使用
    
    return 0;
}

```

##Const关键字

变量是值可以改变的量，但有时，我们不希望变量的值改变，这是需要使用`const`关键字来修饰<font color=red>变量</font>。

```
int const a = 5;
// 或
// const int a = 5;

a = 10; // 这句话是错的，因为a的值已经不可变
```
<font color=red>以上这种const与变量类型交换位置的写法不是任何类型都使用。如指针类型意义就不同。</font>