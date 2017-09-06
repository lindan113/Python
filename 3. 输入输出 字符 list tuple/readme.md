2017-8-29 14:12:31 

# 数据类型

`int`整数类型，`float`浮点类型，`str`字符串类型,`bool`布尔类型
没有long类型，
>类型转换函数：
int()函数：转换成int类型；
float()
str()
bool()  只对0和1

## 输入
input() 
比如：
```
name = input()
```
于是接下来会等待你的输入，赋值给name，input得到的数据类型是`str`，如果要和整数比较要装换成整数类型。

或者
```
name = input('please enter your name')
```
这样会先`打印please enter your name`，然后等待你的输入。交互更好

## 输出
接上
```
print(name)
```
或者打印数字
```
print(100)
print(40+60)
```

# 字符串str
`str` 类型是不可变对象类型

## 字符串切片
字符串'abcdefg'也可以看成是一种list，每个元素就是一个字符
```
'abcdefgefg'[:3]   # 被省略的是0
'abcdefgefg'[::2]	#从头到尾每隔两个取
```
语法：
```
[m:n:p]
```
从第m个开始，每隔p个取，直到第(n-1)个


## 字符串的方法：
- `lower()` 变成全小写字母
- 内建函数`isinstance(x,str)`可以检查`x`是不是`str`类型


# 字符编码
- ASCII编码：一个字节（8bits），127个，有一位奇偶校验
- Unicode：最常用的是用两个字节表示一个字符。最新的Python 3版本中，字符串是以Unicode编码。

- 为了节约字符，有一种可变长的编码 UTF-8，英文字符一个字节，汉字三个字节。
- 在计算机内存中，统一使用**Unicode编码**，当需要保存到硬盘或者需要传输的时候，就转换为**UTF-8编码**。

<img src="./image/记事本编辑.png"/>
<img src="./image/浏览网页.png"/>

语法：
```
<img src="./images/xxx.png"/>
```


----------


# list 列表类型

list 是一个数据结构，数组类型，但是元素的类型可以不相同，比如
```
a = [12,'abc',10.5]
```
注意是中括号
也可以数组嵌套数组
```
b = [ 'a', a, 123, 100 ]
```
如果输入`b[1]`会得到`[12,'abc',10.5]`
输入`b[1][0]`得到`12`

在数组后插入元素`99`
```
a.append(99)
```
在某个位置(比如1号位）插入元素98
```
a.insert(1,98)
```

删除list末尾的元素，用pop()方法;
要删除指定位置的元素，用pop(i)方法，其中i是索引位置：
```
a.pop()
a.pop(1) 
```
   
**输入`a[-1]`得到导数第一个元素，`a[-2]`导数第二个元素，以此类推**


# tuple 元组类型

tuple一旦初始化就不能修改
> tuple的意义：
> 因为tuple不可变，所以代码更安全。如果可能，能用tuple代替list就尽量用tuple。
```
boy = ('Bob','Tom')
```
注意是圆括号
输入 `boy[1]`可以获得元素'Bob'

只有1个元素的tuple定义时必须加一个逗号,为了消除歧义
```
t = (10，)
```
因为如果是`t = (10)`，会当做t被赋值为10，而不是一个元组。

tuple是不能再修改的，除非tuple含有list类型元素
<img src="./image/tuple.png" />

# 条件判断
```
age = 20
if age >= 18:
	print('your age is', age ) 
	print('adult')
elif age <= 12:
	print('child')
else:
	print('sorry')
```

# 循环

## 1. for...in循环
`for x in ...`循环就是把每个元素代入变量x，然后执行缩进块的语句。
例子1：
```
# 累加1到10
sum = 0
number = [1,2,3,4,5,6,7,8,9,10]
for i in number:
	sum = sum + i
print(sum)
```
> 但如果范围更大，比如1到100：
> 有一个函数range()，
> ```
> a = range(4)
> a = list(a)
> ```
> 那就可以把a从原来的range(0,4),即表示从0到不超过4的整数，转换成list类型。

从1加到100代码：
```
sum = 0
for i in range(101)
	sum = sum + i
print(sum)
```

## while循环
从1加到100
```
sum = 0
i = 1
while i <= 100
	sum = sum + 1
	i = i - 1
print(sum)
```

**易错点**
**`for x in ...` 和 `while ...` 后面一定一定有冒号`:`**

