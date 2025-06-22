
# python笔记
## python基础语法
### python保留字
逻辑值 True False None
逻辑运算 and or not
条件控制 if elif else
循环控制 for while break continue
异常处理 try except finally raise
函数定义 def return lambda
类与对象 class del
模块导入 import from as
作用域 global nonlocal
异步编程 async await
其他 assert in is pass with yield
### 注释
单行注释以#开头
多行注释可以用多个#号，还有'''和 """
### 行与缩进
python使用缩进来表示代码块，不需要使用大括号
所进的空格数是可变的，但是同一个代码块的语句必须包含相同的缩进格数
### 多行语句
通常是一行写完一条语句，但如果语句很长，可以使用反斜杠\来实现多行语句
在[] {}或()中的多行语句，不需要使用反斜杠
### 数字类型
int bool float complex
### 字符串
python中使用单引号和双引号完全相同
使用三引号可以指定一个多行字符串
转义符\
反斜杠可以用来转义，使用r可以让反斜杠不发生转义
按字面意义级联字符串
字符串可以用 + 连接在一起，可以用* 重复
python字符串有2种索引方式，从左往右以0开始，从右往左以-1开始
python中的字符串不能改变
python中没有单独的字符类型，一个字符就是长度为1的字符串
字符串切片str[start:end],其中start（包含）是切片开始的索引，end（不包含）是切片结束的索引
字符串的切片可以架上步长参数step， str[start:end:step]
### 空行
函数之间或类的方法之间用空行分隔，表示一段新的代码的开始
类与函数入口之间也用一行空行分隔，以突出函数入口的开始
空行不是python语法的一部分，只是便于维护与重构
空行也是程序代码的一部分
### 同一行 显示多条语句
可以同一行显示多条语句，语句之间用分号；隔开
### 多个语句组成代码组
缩进相同的一组语句构成一个代码块，称之为代码组
if while def 和class这样的符合语句，首行以关键字开始，以冒号：结束，该行之后的一行或多行代码构成代码组
将首行及后面的代码组称为一个子句 clause
### print输出
print默认输出是换行的，如果要实现不换行需要在变量末尾加上 end=" "
### import
将整个模块导入 import somemodule
从某个模块导入某个/多个/全部 from some module import somefunction,somefunction2 / * //done
## 基础数据类型 
python中的变量不需要声明
每个变量在使用前都必须赋值，变量赋值后该变量才会被创建
python中，变量就是变量，没有类型；类型是变量所指的内存中对象的类型
等号用来给变量赋值
等号左边是一个变量名，右边是存储在变量中的值
### 多个变量赋值
允许同时为多个变量赋值
a=b=c=1
a,b,c=1,2,"runoob"
### 标准数据类型
Number 数字
String 字符串
bool 布尔类型
List 列表
Tuple 元组
Set 集合
Dictionary 字典
其中，数字 字符串 元组 为不可变数据
列表 字典 集合 为可变数据
另有高级数据类型，如 字节数组类型 bytes
### 布尔类型
在python中，所有非零的数字和非空的字符串、列表、元组等数据类型都被视为True，只有
0、空字符串、空列表、空元组等被视为False
### 列表
最频繁；可以完成大多数集合类的数据结构实现
列表中的元素可以不相同，支持数字，字符串甚至可以包含列表，即嵌套
列表是写在方括号[]之间、用逗号分隔开的元素列表
和字符串一样，列表同样可以被索引和截取，列表被截取后返回一个包含所需元素的新列表
列表截取的语法格式： 变量[头下标:尾下标]
索引值以零为开始，-1为从末尾的开始位置
列表中的元素可以被改变
### 元组
与列表类似，但元组的类型不能修改；元组写在小括号里，元素之间用逗号隔开
元组中的元素类型也可以不相同
可以把字符串看作一类特殊的元组
虽然tuple的元素不可改变，但它可以包含可变的对象，比如list列表
构造包含0个或1个元素的元组比较特殊
tup1=() #空元组
tup2=(20,) #一个元素20的元组
string list和tuple都属于sequence 序列
元组可以使用+操作符进行拼接
### Set 集合
python中的set集合是一种无序、可变的数据类型，用于存储唯一的元素
集合中的元素不会重复，并且可以进行交集 并集 差集等常见的集合操作
在python中，集合使用大括号{}表示，元素之间用逗号分隔
可以使用set()函数创建集合
注意：创建一个空集合必须用set()而不是{}，因为{}是用来创建一个空字典
创建格式：
parame={value01,value02,...}
或
set(value)
### Dictionary 字典
列表是有序的对象集合，字典是无序的对象集合
区别在于：字典当中的元素是通过键来存取的，而不是通过偏移存取
字典是一种映射类型，用{}标识，它是一个无序的键(key):值(value)的集合
键key必须使用不可变类型
在同一个字典中，键key必须是唯一的
字典是一种映射类型，它的元素是键值对
字典的关键字必须为不可变类型，且不能重复
创建空字典使用{}
### bytes类型
在python3中，bytes类型表示的是不可变的二进制序列 byte sequence
bytes类型种的元素值是整数值（0-255）
bytes类型通常用于处理二进制数据
常见的创建bytes对象方式，使用b前缀
x=b"hello"
bytes()函数创建
x=bytes("hello",encoding="utf-8")
由于bytes类型不可变，在进行修改操作时要创建于给新的bytes对象
### 数据类型转换
数据类型的转换，只需要将数据类型作为函数名即可
隐式类型转换-自动完成
显式类型转换-需要使用类型函数来转换
对两种不同类型的数据进行运算，较低数据类型整数就会转换为较高数据类型浮点数，以避免数据丢失
整形和字符串类型直接运算会报错；需要先进行显式类型转换
int()
float()
str()
通常情况下，python的数据类型高低可以按照如下顺序理解：
布尔bool<整型int<浮点型float<复数complex
这个顺序主要根据数据类型可以表示的信息范围和精度来确定
数据类型的转换并非无限制，取决于原始数据是否能够提供足够的信息来表示目标类型
## python运算符
### 算术运算符
+
-
*
/
% 各个环境下%运算符的含义不一样；c/c++/java为取余；python为取模
ab正负号一致时，取模运算和取余运算得到的结果一致
** 幂，返回x的y次幂
// 取整除，往小的方向取整数
### 比较运算符
== 等于 比较是否相等
!= 不等于
>
<
>=
<=
### 赋值运算符
= 赋值
+=
-=
*=
/=
%=
**=
//=
:= 海象运算符；在表达式中同时进行赋值和返回赋值的值
### python位运算符
& 按位与
| 按位或
^ 按位异或
~ 按位取反
<< 左移
>> 右移
### python逻辑运算符
and 布尔与
or 布尔或
not 布尔非
### python成员运算符
in 如果在指定的序列中找到值返回True，否则返回False
not in
### python身份运算符
is is判断两个标识符是不是引用自一个对象
is not
id()函数用于获取对象的内存地址
### python运算符优先级
## 数字
可以使用del语句删除一些数字对象的引用
python解释器可以作为一个简单的计算器；在解释器里输入一个表达式，它将输出表达式的值
在交互模式中，最后被输出的表达式的结果被赋值给变量_
此处，_变量应被用户视为只读变量
### 数学函数
abs(x) 返回绝对值
ceil(x) 返回数字的上入整数
cmp(x,y) python3已废弃，使用 (x>y)-(x<y>)替换
exp(x) e的x次幂
fabs(x) 以浮点数形式返回数字的绝对值
floor(x) 返回数字的下舍整数
log(x) 取对数
log10(x) 以10为基底取对数
max(x1,x2,...) 返回给定参数的最大值，参数可以为序列
min(x1,x2,...) 最小值
modf(x) 返回x的整数部分与小数部分；两部分的数值符号与x相同，整数部分以浮点型表示
pow(x,y) x**y运算后的值
round(x[,n]) 返回浮点数x的四舍五入值，如给出n值，则代表舍入到小数点后的位数；
保留值将保留到离上一位更近的一端
sqrt(x) 返回数字x的平方根
### 随机数函数
choice(seq) 从序列的元素中随机挑选一个元素
randrange([start,]stop[,step]) 从指定范围内，按指定基数递增的集合中获取一个随机数，基数默认值为1
random() 随机生成下一个实数，它在(0.1)范围内
seed([x]) 改变随机数生成器的种子seed
shuffle(lst) 将序列的所有元素随机排序
uniform(x,y) 随机生成下一个实数，它在[x,y]范围内
### 三角函数
acos(x) 返回x的反余弦弧度值
asin(x)
atan(x)
atan2(y,x) 返回给定的x及y坐标值的反正切值
cos(x) 返回x的弧度的余弦值
hypot(x,y) 返回欧几里得范数sqrt(x*x+y*y)
sin(x)
tan(x)
degrees(x) 将弧度转换为角度
radians(x) 将角度转换为弧度
### 数学常量
pi 圆周率，一般以Π表示
e 自然常数
## 字符串
使用方括号截取字符串以访问字串
变量[头下标:尾下标]
### python字符串运算
+ 连接
* 重复输出
[] 通过索引获取字符串中字符
[:] 截取字符串中的一部分；左闭右开
in 成员运算符，在则True
not in 不在则True
r/R 原始字符串，所有的字符串都是直接按照字面意思来使用，没有转义特殊或不能打印的字符
% 格式字符串
### 字符串格式化
基本用法是将一个值插入到要给有字符串格式符%的字符串中
%c 字符及其ASCII码
%s 字符串
%d 整数
%u 无符号整型
%o 无符号八进制数
%x 无符号十六进制数
%X 大写
%f 浮点数字，可指定小数点后的精度
%e 用科学计数法格式化浮点数
%E 上同
%g %f和%e的简写
%G
%p 用十六进制格式化变量的地址
格式化操作符辅助指令
* 定义宽度或者小数点精度
- 用作左对齐
+ 在整数前面显示加号
<sp> 在正数前面显示空格
字符# 在八进制数前面显示零，在十六进制前面显示0x
0 显示的数字前面填充0而不是默认的空格
% %%输出一个单一的%
(var) 映射变量（字典参数）
m.n. m是现实的最小总宽度，n是小数点后的位数
### fstring
字面量格式化字符串
f-string格式化字符串以f开头，后面跟着字符串，字符串中的表达式用大括号{}包起来
它会将变量或表达式计算后的值替换进去
### Unicode字符串
在python3中，所有的字符串都是unicode字符串
### python字符串的内建函数
capitalize() 将字符串的第一个字符转换为大写
center(width,fillchar) 返回一个指定宽度width居中的字符串，fillchar为填充的字符，默认为空格
count(str,bet=0,end=len(string)) 返回str在string里面出现的次数
bytes.decode(encoding='utf-8',errors='strict')
encode(encoding='UTF-8',errors='strict') 以encoding指定的编码格式编码字符串
endswith(suffix,beg=0,end=len(string)) 检查字符串是否以suffix结束
expandtabs(tabsize=8) 把字符串string中的tab符号转为空格，tab符号默认的空格数是8
find(str,beg=0,end=len(string)) 检测str是否包含在字符串中
index(str,beg=0,end=len(string))
isalnum() 检查字符串是否有字母和数字构成
isalpha() 字母或中文字
isdigit() 只包含数字
islower() 包含且只包含小写字母
isnumeric() 包含且只包含数字字符
isspace() 只包含空格
istitle() 标题化的
isupper() 包含且只包含大写字母
join(seq) 以指定字符串作为分隔符，将seq中所有的元素合并为一个新的字符串
len(string) 返回字符串长度
ljust(width[,fillchar]) 返回一个原字符串左对齐，并使用fillchar填充之长度width的新字符串
lower() 转换字符串中所有大写字符为小写
lstrip() 截掉字符串左边的空格或指定字符
maketrans() 创建字符映射的转换表
max(str) 返回字符串str中最大的字母
min(str)
replace(old,new[,max])
rfind(str,beg=0,end=len(string)) 从右边开始查找
rindex(str,beg=0,end=len(string))
rjust(width[,fillchar])
rstrip()
split(str="",num=string.count(str)) 以str为分隔符截取字符串
splitlines([keepends]) 按照行分隔，返回一个包含各行作为元素的列表
startswith(substr,beg=0,end=len(string)) 检查字符串是否以指定子字符串开头
strip([charts]) 在字符串上执行lstrip()和rstrip()
swapcase() 将字符串中大写转换为小写，小写转换为大写
title() 返回标题化的字符串，即所有单词都是以大写开始，其余字母均为小写
tarnslate(table,deletechars='') 根据table给出的表转换为string字符
upper() 小写转大写
zfill(width) 返回长度为width的字符串，原字符串右对齐，前面填充0
isdecimal() 检查字符串是否只包含十进制字符

## 列表
序列是python中最基本的数据结构
序列中的每个值都有对应的位置值，称之为索引
python有6个序列的内置类型，最常见的是列表和元组
列表可以进行的操作包括 索引 切片 加 乘 检查成员
列表的数据项不需要具有相同的类型
创建一个列表，只要把逗号分隔的不同数据用方括号括起来即可
### 更新列表
可以对列表的数据项进行修改或更新；可以使用append()方法来添加列表项
列表比较需要引入operetor模块的eq方法
### 列表的函数与方法
函数
len()
max(list)
min(list)
list(seq) 将元组转换为列表
方法
list.append(obj) 末尾添加新对象
list.count(obj) 统计某个元素在列表中出现的次数
list.extend(seq) 在列表末尾一次性追加另一个序列中的多个值
list.index(obj) 从列表中找出某个值第一个匹配项的索引位置
list.insert(index,obj) 将对象插入列表
list.pop([index=-1]) 移除列表中的一个元素，默认最后一个元素，并且返回该元素的值
list.remove(obj) 移除列表中某个值的第一个匹配项
list.reverse() 反向列表中的元素
list.sort(key=none,reverse=False) 对原列表进行排序
list.clear() 清空列表
list.copy() 复制列表

## 元组
python的元组与列表类似，不同之处在于元组的元素不能修改
元组使用小括号，列表使用方括号
创建空元组
tup1=()
元组中只包含一个元素时，需要在元素后面添加逗号，否则括号会被当做运算符使用
### 修改元组
元组种的元素值不允许修改，但可以对元组进行连接组合
### 删除元组
元组中的值不允许删除，但可以使用del语句删除整个元组
### 元组内置函数
len(tuple)
max(tuple)
min(tuple)
tuple(iterable) 将可迭代序列转化为元组
### 关于元组是不可变的
所谓元组的不可变指的是元组所指向的内存中的内容不可变
重新赋值元组，会绑定到新的对象，不是修改了原来的对象

## 字典
字典是另一种可变容器模型，且可存储任意类型对象
字典的每个键值对用冒号分隔，每个对之间用逗号分隔
d={key1:value1,key2:value2,key3:value3}
键是唯一的，但值则不必
值可以取任何数据类型，但键必须是不可变的，如字符串，数字
### 空字典
使用大括号创建空字典
使用内建函数dict()创建字典
### 访问字典里的值
把相应的键放入到方括号中
向字典里添加新内容的方法是增加新的键对值
del 语句可以删除单一元素，也能清空字典
dic.clear() 清空字典
### 字典键的特性
字典值可以是任何的python对象，既可以是标准的对象，也可以是用户自定义的，但键不行
不允许同一个键出现两次；创建时如果同一个键被赋值两次，后一个值会被记住
键必须不可变，所以可以用数字，字符串或元组充当，而用列表就不行
### 字典内置函数方法
函数
len(dict) 元素个数，即键的总数
str(dict) 输出字典，可以打印的字符串表示
type(varialbe) 返回输入的变量类型
内置方法
dict.clear()
dict.copy()
dict.fromkeys()
dict.get(key,default=None) 返回指定键的值；不存在则返回默认值
key in dict
dict.items() 以列表返回一个视图对象
dict.keys() 返回一个视图对象
dict.setdefault(key,default=None) 如果键不存在与字典中，将会添加键并将值设为default
dict.update(dict2) 将字典dict2的键值对更新到dict里
dict.values() 返回一个视图对象
dict.pop(key[,default]) 删除字典key所对应的值，返回被删除的值
dict.popitem() 返回并删除字典中的最后一对键和值

## 集合
set是一个无序的不重复元素序列
集合中的元素不会重复，并且可以进行交集，并集，差集等常见的集合操作
可以使用大括号创建集合，元素之间用逗号隔开；使用set()函数创建集合
set1={1,2,3,4}
set2=set([4,5,6,7])
创建一个空集合必须使用set()而不是{}
集合支持集合推导式
### 集合的基本操作
添加元素
s.add(x)
如果元素已存在，则不进行任何操作.
s.update(x) 参数可以是列表 元组 字典等
x可以有多个，用逗号隔开
移除元素
s.remove(x) 元素不存在会发生错误
s.discard(x) 元素不存在不会发生错误
随机删除集合中的一个元素
s.pop()
计算集合元素个数 len(s)
清空集合 s.clear()
判断元素是否在集合中 x in s
### 集合内置方法完整列表
add()
clear()
copy()
different() 返回多个集合的差集
different_update() 移除集合中的元素，该元素在指定的集合也存在
discard() 删除集合中指定的元素
intersection() 返回集合的交集
intersection_update() 返回集合的交集
isdisjoint() 判断两个集合是否包含相同的元素
issubset() 判断指定集合是否为该方法参数集合的子集
issuperset() 判断该方法的参数集合是否为指定集合的子集
pop() 移除随机元素
remove() 移除指定元素
symmetric_different() 返回两个集合中不重复的元素集合
symmetric_difference_update() 移除当前集合中在另外一个指定集合相同的元素，并将另外一个指定集合
中不同的元素插入到当前集合中
union() 返回两个集合的并集
update() 给集合添加元素
len() 计算集合元素个数

## python3 assert 断言
错误和异常
assert用于判断一个表达式 在表达式条件为false的时候触发异常
断言可以在条件不满足程序运行的情况下直接返回错误，而不必等待程序运行后出现崩溃的情况

## python推导式
推导式是一种独特的数据处理方式，可以从一个数据序列结构构建另一个新的数据序列的结构体
适用于生成列表 字典 集合 和生成器
### 列表推导式
[表达式 for 变量 in 列表]
[表达式 for 变量 in 列表 if 条件]
表达式可以是有返回值的函数
### 字典推导式
{key_expr: value_expr for value in collecting if conditon}
### 集合推导式
{expression for item in Sequence if conditional}
### 元组推导式 生成器表达式
(expression for item in Sequence if conditional)
元组推导式返回的是一个生成器对象

## python lambda
使用lambda创建匿名函数
lambda函数是一种观念小型的 匿名的 内联函数 可以具有任意数量的参数 但只能有一个表达式
匿名函数不需要使用def关键字定义完整函数
语法格式
lambda arguments:expression

尝试本地更新

## 条件控制
if condition1:
    statement_block_1
elif condition2:
    statement_block_2
else:
    statement_block_3
python中用elif代替了else if，所以if语句的关键字为 if-elif-else
每个条件后面都要使用冒号： 表示接下来是满足条件后要执行的语句块
使用缩进来划分语句块 相同缩进数的语句在一起组成一个语句块
python中没有switch...case语句，但添加了match...case，功能类似
可以吧if...elif...else结构放在另外一个if...elif...else结构中，即if嵌套
### match...case
match后的对象会一次与case后的内容进行匹配，如果匹配成功，则执行匹配到的表达式，否则直接跳过
_可以匹配一切  
语法格式如下  
```
match subject:  
    case <pattern_1>:  
        <action_1>  
    case <pattern_2>:  
        <action_2>  
    case <pattern_3>:  
        <action_3>  
    case _:  
        <action_wildcard>  
```
case _:类似于C和Java中的default，当其他case都无法匹配时，匹配这条，保证永远会匹配成功  
```
def http_errpr(status):
    match status:
        case 400:
            return "Bad reuest"
        case 404:
            return "Not found"
        case 418:
            return "I'm a teapot"
        case _:
            return "Something's wrong with the internet"

mystatus=400
print(http_error(mystatus))
```
一个case也可以设置多个匹配条件，条件使用|隔开
```
...
    case 401|402|403:
        return "Not allowed"
```
## python3循环语句
### while循环
python中while语句的一般形式：
```
while 判断条件（condition）：
    执行语句（statements）...
```
python中没有do...while循环
### 无限循环
可以通过设置条件表达式永远不为false来实现无限循环
使用CTRL+C来退出当前的无限循环
无限循环在服务器上客户端的实时请求非常有用
## while循环使用else语句
如果while后面的条件语句为false时，则执行else语句块
```
while <expr>:
    <statement(s)>
else:
    <additional_statement(s)>
```
循环输出数字，并判断大小
```
count=0
while count<5:
    print(count,'小于5')
    count=count+1
else:
    print(count,'大于或等于5')
```
### 简单语句组
类似if语句的语法，如果while循环体中只有一条语句，可以将该语句与while写在同一行中
```
flag=1
while(flag): print('欢迎访问菜鸟教程！')
print("Good bye!")
```
### for语句
python for循环可以遍历任何可迭代对象，如一个列表或者一个字符串
```
for <variable> in <sequence>:
    <statements>
else:
    <statements>
```
for...else的用法与while...else类似  
整数范围值可以配合range()函数使用，左闭右开
```
#1到5的所有数字
for number in range(1.6):
    print(number)
```
### for...else
python中，for...else...用于在循环结束后执行一段代码
```
for item in iterable:
    #循环主体
else:
    #循环结束后执行的代码
```
当循环执行完毕，即遍历完iterable中的所有元素后，会执行else子句中的代码，如果在循环过程中
遇到了break语句，则会中断循环，此时不会执行else子句
### range()函数
可以使range()以指定数字开始并指定不同的增量（甚至可以是负数，即步长）
```
for i in range(0,10,3)
    print(i)
```
可以结合range()和len()函数以遍历一个序列的索引  
可以使用range()函数来创建一个列表
### break和continue语句及循环中的else子句
break语句可以跳出for和while循环体  
如果从for或while循环中终止，任何对应的循环else块将不执行  
continue语句被用来告诉python跳过当前循环块中的剩余语句，然后继续进行下一次循环  
循环语句可以有else子句，在穷尽列表（for循环）或条件变为false（while循环）导致循环终止时被执行  
但循环被break终止时不执行
### pass语句
空语句，保持程序结构的完整性  
不做任何事情，一般用作占位语句
## 编程第一步
### end关键字
关键字end可以将结果输出到同一行，或者在输出的末尾添加不同的字符

## python推导式
python推导式是一种独特的数据处理方式，可以从一个数据序列构建另一个新的数据序列的结构体  
python推导式是一种强大且简洁的语法，适用于生成列表 字典 集合和生成器  
在使用推导式时，需要注意可读性，尽量保持表达式简洁，以免影响代码的可读性和可维护性
### 列表推导式
```
[表达式 for 变量 in 列表]
或者
[表达式 for 变量 in 列表 if 条件]
```
### 字典推导式
```
{key_expr:value_expr for value in collection}
或
{key_expr:value_expr for value in collection if condition}
```
### 集合推导式
```
{expression for item in Sequence}
或
{expression for item in Sequence if conditional}
```
### 元组推导式（生成器表达式）
元组推导式可以利用range区间 元组 列表 字典和集合等数据类型 快速生成一个满足指定需求的元组
```
(expression for item Sequence)
或
(expression for item in Sequence if conditonal)
```
元组推导式和列表推导式用法完全相同  
元组推导式用()括起来，列表推导式用的是[]
元组推导式返回的结果是一个生成器对象
可以使用 tuple()函数，直接将生成器对象转换成元组  
### 根据判断条件生成不同列表的推导式
```
result1 if condition else result2 for variable in originlist
list1=['python','test1','test2']
list2=[word.title() if word.startwith('p') else word.upper() for word in list1]
print(list2)
```
## python迭代器与生成器
### 迭代器
迭代是python最强大的功能之一 是访问集合元素的一种方式  
迭代器是一个可以记住遍历的位置的对象  
迭代器对象从集合的第一个元素开始访问，直到所有的元素被访问完结束  
迭代器只能往前不会后退
迭代器有两个基本方法 iter() next()  
字符串 列表或元组对象都可用于创建迭代器  
迭代器对象可以使用常规for语句进行遍历  
也可以使用next()函数

#### 创建一个迭代器  
把一个类作为一个迭代器使用需要在类中实现两个方法 __iter__() __next__()  
类都有一个构造函数 python的构造函数为 __init__() 它会在对象初始化的时候执行  
__iter__() 方法返回一个特殊的迭代器对象 这个迭代器对象实现了__next__()方法并通过
StopIteration异常标识迭代的完成  
__next__()方法会返回下一个迭代器对象  
```
#创建一个返回数字的迭代器，初始值为1，逐步递增1：
class MyNumbers:
    def __iter__(self):
        self.a=1
        return self
    
    def __next__(self):
        x=self.a
        self.a+=1
        return x   

myclass=MyNumbers()
myiter=iter(myclass)

print(next(myiter))
print(next(myiter))
print(next(myiter))
print(next(myiter))
print(next(myiter))
```
#### StopIteration
StopIteration异常用于标识迭代的完成 防止出现无限循环的情况  
在__next__()方法中可以设置在完成指定循环次数后触发StopIteration异常来结束迭代  
```
class MyNubers:
    def __iter__(self):
        self.a=1
        return self
    
    def __next__(self):
        if self.a<=20:
            x=self.a
            self.a+=1
            return x
        else:
            return StopIteartion

myclass=MyNumbers()
myiter=iter(myclass)

for x in myiter:
    print(x)
```
### 生成器
在python中 使用了yield的函数被称为生成器 generator  
yield是一个关键字 用于定义生成器函数  可以在迭代过程中逐步产生值，而不是一次性返回所有结果  
生成器是一个返回迭代器的函数，只能用于迭代操作；即生成器就是一个迭代器  
当在生成器函数中使用yield语句时，函数的执行将会暂停，
并将yield后面的表达式作为当前迭代的值返回  
每次调用生成器的next()方法或使用for循环进行迭代时，函数会从上次暂停的地方继续执行，
直到再次遇到yield语句。这样，生成器函数可以逐步产生之，而不是一次性计算并返回所有结果  
调用一个生成器，返回的是一个迭代器  
```
#生成器函数的使用
#定义生成器函数
def countdown(n):
    while n>0:
        yield n
        n-=1
#创建生成器对象
generator=countdown(5)

#通过迭代生成器获取值
print(next(generator)) #输出5
print(next(generator)) #输出4
print(next(generator)) #输出3

#使用for循环迭代生成器
for value in generator:
    print(value) #输出：2 1
```

```
#使用yield实现斐波那契额数列
import sys
def fibonacci(n):
    a,b,counter=0,1,0
    while True:
        if(counter>n):
            return
        yield a
        a,b=b,a+b
        counter+=1
f=fibonacci(10)

while True:
    try:
        print(next(f),end=' ')
    except StopIteration:
        sys.exit()
```
## python3 with
处理文件操作 数据库连接等需要明确释放资源的场景  
with是python中的一个关键字，用于上下文管理协议 context management protocol  
简化了资源管理代码，特别是那些需要明确释放或清理的资源 如文件 网络连接 数据库连接等  

with语句的优势  
自动释放资源  
代码简洁  
异常安全  
可读性强  

### with语句基本语法
```
with expression [as variable]:
    #代码块
```
其中，expression返回一个支持上下文管理协议的对象  
as variable 是可选的，用于将表达式结果赋值给变量   
代码块执行完毕后，自动调用清理方法  

文件操作示例  
最常见的with语句应用场景是文件操作
```
with open('example.txt','r') as file:
    content=file.read()
    print(content)
#文件已自动关闭
```
### with语句的工作原理
with语句背后是python的上下文管理协议，该协议要求对象实现两个方法  
__enter__() 进入上下文时调用，返回值赋给as后的变量  
__exit__() 退出上下文时调用，处理清理工作  
### 异常处理机制
__exit__()方法接收3个参数  
exc_type: 异常类型  
exc_val: 异常值  
exc_tb: 异常追踪信息  
如果__exit__()返回True，则表示异常已被处理，不会继续传播；
返回False或None，异常会继续向外传播 **#向外传播是什么意思？**
### 实际应用场景
文件操作
```
#同时打开多个文件
with open('input.txt','r') as infile, open('output.txt','r') as outfile:
    content=infile.read()
    outfile.write(content.upper())
```
数据库连接
```
import sqlite3
with sqlite3.connect('database.db') as conn:
    cursor=conn.cursor()
    cursor.execute('SELECT * FROM users')
    results=cursor.fetchall()
#连接自动关闭
```
线程锁
```
import threading
lock=threading.Lock()
with lock:
    #临界区代码
    print('这段代码是线程安全的')
```
临时修改系统状态
```
import decimal
with decimal.localcontext() as ctx:
    ctx.prec=42 #临时设置高精度
    #执行高精度计算
#精度恢复原设置
```
### 创建自定义的上下文管理器
类实现方式  
可以通过__enter__和__exit__方法创建自定义的上下文管理器  
```
class Timer:
    def __enter__(self):
        import time
        self.start=time.time()
        return self
    def __exit__(self,exc_type,exc_val,exc_tb):
        import time
        self.end=time.time()
        print(f"耗时：{self.end-self.start:.2f}秒")
        return False
#使用示例
with Timer() as t:
    #执行一些耗时操作
    sum(range(1000000)) #sum()是什么？
```
使用contextlib模块  
python的contextlib模块提供了更简单的方式来创建上下文管理器
```
from contextlib import contextmanager

@contextmanager
def tag(name):
    print(f"<{name}>")
    yield
    print(f"/<{name}>")
#使用示例 这个示例是干嘛的？
with tag("h1"):
    print("这是一个标题")
```
### 常见问题与最佳实践
常见错误  
错误的认为with只能用于文件  
```
conn=sqlite3.connect('db.sqlite')
#应该使用with语句
```
忽略__exit__的返回值
```
class MyContext:
    def __exit__(self,exc_type,ext_val,exc_tb):
        #忘记返回True/False可能导致异常处理不符合预期
        pass
```
最佳实践  
优先使用with管理资源：对于文件 网络连接 锁等资源 总是优先考虑使用with语句  
保持上下文简洁 with块中的代码应该只包含与资源相关的操作  
合理处理异常 在自定义上下文管理器中，根据需求决定是否抑制异常  
利用多个上下文  python允许在单个with语句中管理多个资源

### 总结要点
自动管理资源 with语句确保资源被正确释放  
上下文协议  需要实现__enter__和__exit__方法  
异常安全  即使代码块中出现异常，资源也会被释放  
常见应用 文件操作 数据库连接 线程锁等  
自定义实现 可以通过类或contextlib创建自定义上下文管理  
## python3函数
函数是组织好的 可重复使用的 用来实现单一 或相关联功能的代码段  
函数能提高应用的模块性 和代码的重复利用率  
### 定义一个函数
规则  
函数代码块以def关键字开头 后接函数标识符名称和圆括号()  
任何传入参数和自变量必须放在圆括号中间 圆括号之间可以用于定义参数  
函数的第一行语句可以选择性地使用文档字符串 用于存放函数说明  
函数内容以冒号：起始 并且缩进  
return [expression]结束函数 选择性地返回一个值给调用方
不带表达式的return相当于返回None  
语法  
```
def 函数名(参数列表)：
    函数体
```
默认情况下 参数值和参数名称是按函数声明中定义的顺序匹配起来的  
### 函数调用
定义一个函数 给了函数一个名称 指定了函数里包含的参数 和代码块结构  
函数基本结构完成后，可以通过另一个函数调用执行 也可以直接从python命令提示符执行  
### 参数传递
在python中 类型属于对象 对象有不同类型的区分 变量是没有类型的  
变量仅仅是一个对象的引用（一个指针）
可以是指向list类型对象 也可以是指向string类型对象  
可更改mutable与不可更改immutable对象  
在python中，strings tuples和numbers是不可更改的对象
而list dict等则是可以修改的对象  
不可变类型 a=5 a=10
新生成一个int值对象10 再让a指向它 而5被丢弃 不是改变a的值 相当于新生成了a  
可变类型 la=[1,2,3,4] la[2]=5
将list la的第三个元素值更改 本身la没有动 只是其内部的一部分值被修改了  
python函数的参数传递  
不可变类型 类似C++的值传递 如整数 字符串 元组
fun(a)传递的只是a的值 没有影响a对象本身 如果在fun(a)内部修改a的值
则是新生成一个a的对象  
可变类型 类似C++的引用传递 如 列表 字典 如fun(la) 则是将la真正地传过去
修改后fun外部的la也会收到影响  
python中的一切都是对象 严格意义不能说值传递还是引用传递
应该说传不可变对象和传可变对象  
### 参数
调用函数时可使用的正式参数类型  
必须参数  
关键字参数  #就是在函数调用时才进行定义与赋值的参数？  
默认参数  #在函数定义时形参处通过赋值给参数默认值
不定长参数  
必须参数 须以正确的顺序传入函数 调用时的数量必须和声明时一样  
关键字参数 函数调用使用关键字参数来确定传入的参数值  
使用关键字参数允许调用时参数的顺序与声明不一致
因为python解释器能够用参数名匹配参数值  
默认参数 调用函数时，如果没有传递参数 则会使用默认参数  
不定长参数  一个函数能处理比当初声明时更多的参数 声明时不会命名
```
def functionname([formal_args,] *var_args_tuple):
    "函数_文档字符串"
    function_suite
    return [expression]
```
加了星号*的参数会以元组(tuple)的形式导入，存放所有未命名的变量参数
```
#可写函数说明
def printinfi(arg1, *vartuple):
    "打印任何传入的参数"
    print("输出：")
    print(arg1)
    print(vartuple)
#调用printinfo函数
printinfo(70,60,50)
```
如果在函数调用时没有指定参数 他就是一个空元组
可以不向函数传递未命名的变量  
```
def printinfo(arg1, *vartuple):
    print("Output:")
    print(arg1)
    for var in vartuple:
        print(var)
    return
printinfo(10)
printinfo(70,60,50)
```
参数带两个星号 ** 基本语法  
```
def functionname([formal_args,] **var_args_dict):
    "函数_文档字符串"
    function_suite
    return [expression]
```
加了两个星号**的参数会以字典的形式导入
```
def printinfo(arg1, **vardict):
    print("Output:")
    print(arg1)
    print(vardict)
printinfo(1,a=2,b=3)
```
声明函数时，参数中星号*可以单独出现
```
def f(a,b,*,c):
    return a+b+c
```
如果单独出现星号* 则星号*后的参数必须用关键字传入
```
def f(a,b,*,c):
    return a+b+c

f(1,2,3) #报错
f(1,2,c=3) #正常
```
### 匿名函数
python使用lambda来创建匿名函数  
所谓匿名 意即不再使用def语句这样标准的形式定义一个函数  
lambda只是一个表达式 函数体比def简单很多  
lambda的主体是一个表达式 而不是一个代码块 仅仅能在lambda表达式中
封装有限的逻辑进去  
lambda函数拥有自己的命名空间 且不能访问自己参数列表之外或全局命名空间里的参数  
虽然lambda函数看起来只能写一行 却不等同于C或C++的内联函数
内联函数的目的是调用小函数时不占用栈内存从而减少函数调用的开销 提高代码的执行速度  
语法  
```
lambda [arg1[,arg2,......argn]]:expression
```
```
x=lambda a:a+10
print(x(5))
```
```
sum=lambda arg1,arg2:arg1+arg2
print("相加后的值为",sum(10,20))
print("相加后的值为",sum(20,20))
```
可以将匿名函数封装在一个函数内，这样可以使同样的代码来创建多个匿名函数  
以下实例将匿名函数封装在myfunc函数中 通过传入不同的参数来创建不同的匿名函数
```
def myfunc(n):
    return lambda a:a*n

mydoubler=myfunc(2)
mytripler=myfunc(3)

print(mydoubler(11))
print(mytripler(11))
```
### return语句
return [expression]语句用于退出函数
选择性地向调用方返回一个表达式
不带参数值的return语句返回None  
### 强制位置参数
python3.8新增了一个函数形参语法 / 用来指明函数形参必须使用指定位置参数
不能使用关键字参数的形式
```
def f(a,b,/,c,d,*,e,f):
    print(a,b,c,d,e,f)
```
上面例子中
形参a和b必须使用指定位置参数
c或d可以是位置形参或关键字形参
而e和f要求为关键字形参