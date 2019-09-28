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

import用于导入需要的文件，譬如需要`numpy`，这个第三方库，

在创建的.py文件首行直接导入即可，同时有时有些库的命名很长，可是使用`import  as `来简化

有时只需要某个库里面的一个方法，可以这样导入`from   import `

导入之后，这些库的功能就全部都能当前的.py文件中使用了

```python
import numpy
import matplotlib as mlt
from math import log
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

##### float的运算

其和上诉的整数运算一致，但是与一个地方需要注意

```python
>>> 3*0.1  
0.30000000000000004
>>> 0.2 + 0.1 
0.30000000000000004
```

所有语言都存在这种问题。 Python 会尽力找到一种方式,以尽可能精确地表示结果,但鉴于计算机内部表示数字的方式,这在有些情况下很难



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

##### 字符串的常用操作：

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

### Reference

* Python学习笔记(上卷)
* 菜鸟教程