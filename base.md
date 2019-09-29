## Python中的基础必知必会

### 注释：

*注释* 是任何存在于 `#` 号右侧的文字，其主要用作写给程序读者看的笔记。

举个例子：

```python
print('Hello 小巴拉') #这里是一个print 是一个函数
```

或者：

```python
# 这里是一个print函数
print("Hello 小巴拉")
```

注释的作用：

* 解释假设
* 说明重要的决定
* 解释重要逻辑
* 说明编写的程序中的重点难点等

### 命名方式

* 硬性规则：
  * 变量名只能包含字母、数字和下划线。变量名可以字母或下划线打头,但不能以数字打头,例如,可将变量命名为 message_1 ,但不能将其命名为 1_message 。
  * 变量名不能包含空格，但可使用下划线来分隔其中的单词。例如,变量名 greeting_message 可行,但变量名 greeting message 会引发错误。
  * 大小写敏感
* 不要将 Python 关键字和函数名用作变量名,即不要使用 Python 保留用于特殊用途的单词,如 print 
  * 变量名应既简短又具有描述性。例如, name 比 n 好, student_name 比 s_n 好, name_length 比 length_of_persons_name 好。
  * 慎用小写字母 l 和大写字母 O ,因为它们可能被人错看成数字 1 和 0 。
  
* 详细的命名规则可参考如下：

  * [python-style-guide](https://python-guide.gitbooks.io/python-style-guide/content/style-guide/variables.html)
  * [Google 开源项目风格指南](https://zh-google-styleguide.readthedocs.io/en/latest/google-python-styleguide/python_style_rules/)




### import

- 可以通过输入import关键字来导入模块

```
import numpy
```

- 或者使用简称，即将模块通过as关键字来命名一个简称

```
import numpy as np
```

- 有时不必导入整个模块，就像

```
from scipy.stats import norm
```

可以使用`imort this`导入Tim Peters撰写的`Python之禅`



### 变量

```python
balabala = 'weikunkun'
print(balabala)
```

上面程序添加了一个`balabala`变量，对于变量而言，每个变量都存储了一个值---与变量相关的信息，这里存储的值为`weikunkun`。



### Python中的内置类型

对于内置的基本数据类型，可简单分为`数字`、`序列`、`映射`、和`集合`等几大类，这为一种分类方式，另外根据其实例化（如 a=4就是一个实例化）的内容可否被更改，还可以分为`可变`和`不可变`

在Python中有6中标准的数据类型：

* Number
* String
* List
* Tuple
* Set
* Dictionary

其中在六个标准数据类型中

* **可变数据** : Number、String、Tuple
* **不可变数据** : List、Dictionary、Set

#### Number

Python3 支持 **int、float、bool、complex（复数）**。

在Python 3里，只有一种整数类型 int，表示为长整型，没有 python2 中的 Long。

像大多数语言一样，数值类型的赋值和计算都是很直观的。

内置的 type() 函数可以用来查询变量所指的对象类型。

```python
a, b, c, d = 20, 5.5, True, 5+3j
print("a type is {}, b type is{}, c type is {}, d type is {}".format(type(a), type(b), type(c), type(d)))    
## a type is <class 'int'>, b type is<class 'float'>, c type is <class 'bool'>, d type is <class 'complex'>

```

##### 运算

一些常见的数学运算，在Python中可以快速的实现

| 名字 | 符号 | 例子           |
| ---- | ---- | -------------- |
| 加   | +    | 1 + 2          |
| 减   | -    | 2-1或者1-2     |
| 乘   | *    | 3*34           |
| 除   | /    | 分母不能为0    |
| 指数 | **   | 2**6(2的6次方) |

但是除法需要注意一下

```python
>>> 1+2
3
>>> 3*2
6
>>> 2-1
1
>>> 3/2 # 单个/ python均会返回float的数据类型
1.5
>>> type(3/2)
<class 'float'>
>>> 3//2 # 用于取整，返回int类型,去除小数部分，无视四舍五入
1
>>> 15%6 # 用于求余数
3
```

##### float的一些知识

float的运算其和上述的整数运算一致，但是与一个地方需要注意

```python
>>> 3*0.1  
0.30000000000000004
>>> 0.2 + 0.1 
0.30000000000000004
```

所有语言都存在这种问题。 Python 会尽力找到一种方式,以尽可能精确地表示结果,但鉴于计算机内部表示数字的方式,这在有些情况下很难

**float精度控制**

有时候，需要保留小数点的后几位进行精度的空值

```python
>>> a = 1.9935
>>> # round(arg1, arg2) 
>>> # arg1: 传入的float值 # arg2: 保留位数
>>> round(a, 2)
1.99
```



##### 其他的高阶运算

可以使用通过`impor math`进行计算，譬如计算绝对值、求sin、cos、log等

如计算log

```python
>>> import math
# log(arg1, arg2)
# arg1: 计算的值 arg2: 对应的底
>>> log(100, 10)
2.0
>>> log(128, 2)
7.0
>>> log(9, 3)
2.0

```

#### String(字符串)

字符串就是一系列字符，Python中凡是用引号括起来的都是字符串，其中引号可以是`单引号` `双引号` `三引号`都可以

**字符串全部改为大写，或者全部为小写**

```python
>>> name = 'Xiao Bala'
>>> print(name.upper())
XIAO BALA
>>> print(name.lower())
xiao bala
```

**合并(拼接)字符串**

```python
>>> name1 = "Xiao Bala"
>>> name2 = 'Da Bala'
>>> combine_name = name1 + name2
>>> print(combine_name)
'Xiao BalaDa Bala'
```

##### 使用\t \n来组织输出，使其更易读

* \t的效果

```python
>>> print("Dabala")
Dabala
>>> print("\tDabala")
	Dabala
```

* \n的效果

```python
>>> print("Name: \nDabala\nWeikunkun")
Name:
Dabala
Weikunkun
```

##### 使用strip删除字符串中过多的空白

对于程序而言‘Dabala’和’Dabala  '是两个不一样的字符串，所以有时候数据处理的时候，需要进行处理

```python
>>> name = 'Dabala '
>>> name
'Dabala '
>>> name.rstrip()
'Dabala'
```

同理`lstrip`用于删除左边过多的空格，当然也可用`strip`去除所有的空格

##### 使用str()避免类型错误

有时候，会在输出中使用多中类型的变量，譬如，祝福某人生日快乐

```python
age = 23
blessing = 'Happy' + age + 'rd Birthday'
print(blessing)
```

这个输出之后，会发现是错误的，并且提示`TypeError`，这说明了Python无法识别你使用的信息，因为这是字符串和整数两个类型的变量，Python可能会将`age`变量理解为数值`23`或者是字符`2`和 `3` ，所以为了能够让Python能够正常理解，需要将整数类型的age，转化为字符串类型，

```python
age = 23
blessing = 'Happy' + str(age) + 'rd Birthday'
print(blessing)
```

这时候，还可以使用`type(str(age))`，观察其是否真的是字符串类型。

##### 字符串的一些常用的方法

* capitalize()

  将字符串的第一个字母变成大写，其他的字母变小写

  ```python
  >>> name = 'my name IS Xiao Bala'
  >>> name.capitalize()
  My name is xiao bala
  ```

* center()

  用于居中

  ```python
  >>> ## center(width, fillchar)
  >>> ## width: 字符串的总长度 fillchar: 填充的字符
  >>> ## 例如 将name字符变为长度为50的字符串，然后居中，其余的位置*填充
  >>> name = 'Xiao Bala'
  >>> name.center(50, '*')
  '***************my name IS Xiao Bala***************'
  >>> len(name.center(50, '*'))## len方法用于查看变量的长度
  50
  ```

* count()

  用于统计字符串中某个字符出现的次数，或者某个子字符串出现的个数

  ```python
  >>> name = 'my name IS Xiao Bala'
  >>> name.count("a")
  4
  >>> name = 'hello  hello , my my name' 
  >>> name.count('hello')
  2
  >>> #其也可以指定字符串的索引位置，进行统计，关于索引后面会讲到
  >>> name.count('hello', 0, 14) 
  2
  >>> name.count('hello', 0, 10)
  1
  ## hello  hello , my my name
  ## 0123456789....
  ## 以此类推，计算机中，都是从0开始进行计数
  ```

  

* find()

  寻找字符串中是否含有某个字符或者字符串，并返回第一次出现的位置

  ```python
  >>> # HelloXiaobala
  >>> # 0123456789....
  >>> name = 'HelloXiaobala'
  >>> name.find('H')
  0
  >>> name.find('a')
  7
  >>> name.find('o')
  4
  ```





####  

### Reference

* Python学习笔记(上卷)
* 菜鸟教程
* Python编程从入门到实践

