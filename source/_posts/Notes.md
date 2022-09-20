---
title: Notes
---
### Lecture 1 Welcome! 
第一个Lecture是cs61a(sp22)唯一一节没有视频的讲座，其主要内容是介绍课程结构，教授及TA的信息，及部分计算机科学的学科历史发展。忽略此lecture对后面知识部分的讲解并无影响，如想观看请访问[2020版本lecture1](https://www.youtube.com/watch?v=CoHCUimLmdM)。

### Lecture 2 Functions 
#### Expression
Expression中文即为表达式，即包含值（value）和/或运算符，并可以求得值的组合。如：1是一个值，它就等于1；2+3包含值和运算符，并可以求得它们的值等于5。

Call expression是一种组合表达式，意思是将表达式带入到函数当中。对于evaluate call expression最重要的一点就是要记住永远先算运算值（Operand）。

#### Names，Assignment, and User-Defined Functions
>Assignment 是一个把值（value）绑定给名字（names）的过程，而functions 是一个把表达式（expression）和名字（names）绑定的过程。

Environment像一个档案室（memory）把这些绑定记录下来。

#### Environment Diagrams
Environment Diagrams就是档案室（menory）的一个个档案盒（frame），它每次会展现这个档案盒里所有的绑定。

#### Define Fuction
每次当我们自定义一个函数（Define Function）时，我们就在大档案盒里（parent frame）创建了一个小档案盒（child frame）
当我们使用这个函数的时候（call expression）我们会把值（value）放在它所在档案盒（current frame）里运算。

写在第一课结尾的一些话：
学习cs61a的你可能有一点点或者没有编程的基础，面对多如牛毛的概念和定义，感觉到有些势不可挡无法招架，甚至一个定义里的一些名词就是另外一个新的定义，不知无从学起。不过不用担心，这是学习计算机的必经之路，大家初学之时，因为知识没有形成体系，彼此之间没有形成关联，所以感觉繁杂难懂。假以时日，厚积薄发，当你学完cs61a之时，虽前路依然漫漫，但手中的火把却已经点燃。

### Lecture 3 Control
#### Print and None
None 在python当中表示这个值没有任何定义，即没有东西（Nothing）。

Pure functions就像数学里的函数一样，给它一个值，它就只会返回给你一个值（这个值可以为None）。而None-pure functions，除了返回给你一个值（可以为None）以外，它还会干一些其他的事情，比如打印（print）。注意：不要因为print返回的值为None，就忽略了作为一个函数（function）本身的工作--输出一个与输入的值相对应的值。

#### Multiple Environments
每次当我们使用（call）一个方法（function）时我们就会创建一个新的小档案盒（frame），即使我们使用了同一个方法（fucntion）两次，我们也会创建两个不同的小档案盒（frame）。

#### Miscellaneous Python Features
docstring就是一个注释解释这个函数（fucntion）是干什么的。docstring里面包含的doctests，特别的举例出，当我们应用这个函数（function）时，会有什么样的效果或者返回值（return value）。

#### Conditional Statements
statement就是执行某项任务的一个代码语句。compound statement就是一个包含其他语句（statement）的语句（statement）。在conditional statement里面，最终只会有一个选项（suite）被执行。

在Python中，False value 包含：False，0，“ ”（空的string），None。其余的值均为真（true）。

#### Iteration
iteration就是一个循环，它会首先判断这个循环是否满足一个特定的条件（这个条件是自己定义的），如果满足循环则开始，每一次循环结束的时候它会返回开头，再重新判断是否满足条件，如满足，循环继续，反之，循环终止。

### Lecture 4 Higher-Order Functions
#### Design Functions
函数（fucntion）的domain就是函数的定义域，即自变量可以是什么值；函数（fucntion）的range就是函数的值域，即函数的因变量可能是什么。

Professor John DeNero给出的设计函数（function）三原则：
    
    - 给每个函数exactly一个工作
    - 不要重复定义一个同样的东西，因为一个函数可以被执行无数次
    - 定义的不同函数时，要遵循一个同样的标准

#### What are Higher-Order Fucntions
高阶函数（higher-order function）的指它的的输出值（return value）或/和 输入值（arguemnt）包含另一个函数的函数。在课上的例子中，教授用高阶函数来归纳一些列有相同作用的函数，如多边形的面积公式都可总结为：系数*r^2

#### Lambda Function
lambda function用来临时创建一个新的函数，但不会给它一个具体的名字。

#### Control Expression
逻辑推理 and 和 or的用法

if语句的便捷写法：
    
    (consequent) if (predicate) else (alternative)

    (结果) if （前提）else （替代方案）

### Lecture 5 Environments
本节课前半部分复习了之前几个lecture与Environments有关的内容。

#### Function Currying
Curry是一个数学家的名字，而function currying的意思就是函数柯里化（好的，这句话并没有解释什么是柯里化。）

柯里化的意思就是说，一个函数利用返回另外一个或多个可以接收参数的sub函数来变向的分层次的接收多个参数。

### Lecture 6 Design
#### Errors & Tracebacks
Syntax Error:语法错误等会在程序运行前就被python发现

Runtime Error(Traceback):会被python编译器在运行时发现

而逻辑错误或者结果错误，python编译器本身并不会提醒

#### String Interpolation
利用 f'{}'的格式，在字符串里加入一串可以运行的代码，这个语法仅限python。在其他编程语言中，会有不同的语法来实现字符串插入值（String Interpolation）
    >>>pi = 3.14
    >>>example = f'pi starts with {pi}'
    >>>print(example)
    pi starts with 3.14

### Lecture 7 Function Examples
复习了之前的内容

### Lecture 8 Exceptions
Exceptions帮助我们处理errors。当遇到未知的错误时，exceptions可以帮我们跳到下一段代码来处理这个错误，以免程序因为未知错误而停止。

>exceptions有关内容没有深入理解，值得进一步探索

### Lecture 9，10 Recursion & Tree Recursions
cs61a里最重要的一个概念之一，递归（recursion）就是在一个函数中调用了这个函数体自己。

写recursion的秘诀：在function body中假设这个function能用。

    Updates via assignment become arguments to a recursive call.

inverse_cascade真的是yyds

### Lecture 11 Containers
Range 本质就是一个由integer组成的list

list comprehension就是用for和if来自己写一些条件，python就会帮你生成一个符合条件的list

### Lecture 12 Dictionaries + More Lists
Dictionary 是无序的就像大麻袋里一个个写了名字（key）的小袋子，你只能通过他们的名字（key）来查看里面的value。

Slicing 创建了一个新的list，并没有改变原先list的值或长短

### Lecture 13 Mutability
mutability22版看不了，这里贴一个21版[2021版Mutability](https://www.youtube.com/watch?v=4qB6086YZV8&list=PL6BsET-8jgYWT-sycOvgSR1Rxj-xXcXGe)

#### Objects
Objects就是对一个物体抽象的表达，通过编码的方式来让一个object状态和行为像它所表达的东西。

#### Mutation 
Any function can refer to something in the global frame.所有的函数都可以访问任何在global frame里面的东西

list.pop()去除并return列表的最后一个元素
list.remove('a')去除并return指定元素
list.append('a')添加一个元素，不return
list.extend([])添加一个序列里的所有元素，不return
list.insert(i, 'a') 在index i的位置添加元素‘a’

### Lecture 14 Objects
每次当我们用class当作模版创建一个新的object的时候，__init__方法就会自动被调用来创建一个新的object

attribute 
dot expression
mathod 

### Lecture 15 Inheritance
Inhiritance represents a "is a" relationship Eg. A checking account is also an account

Composition represents a "has a" relationship Eg. Bank has a account

### Lecture 16 Composition, Representation
repr()可以把一个object转换成python编译器可以理解的string，kind of like JSONStringfy, 而eval()是repr()的逆函数

非常复杂的__string__和__repr__等特殊函数，没仔细看

### EXTRA 1 SQL
-declaritive language, 如sql，prolog 使用者直接写出想要的结果，编译器负责generate
-imperative language 如python java等主流语言，使用者写出计算过程和步骤，编译器负责执行计算

select创建一个新的表来显示
    select [expression] as [name], [expression] as [name];
union用来concat两个表格

create创建一个reuseable表格
    create table [name] as [select statement];

#### projecting new tables from existing ones 
    select [columns] from [table] where [condition] order by [order]

### EXTRA 2 Efficiency
Memoization 就是给函数装一个cashe如果算过了就跳过，可以减少重复计算

Big O notation

Space -- Environments that are active