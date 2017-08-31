
# 函数

## 位置参数
定义函数名，参数
例子，一个my_abs函数：
```
def my_abs(x):
	if x > 0:
		return x
	else:
		return -x
```
调用函数：`my_abs(-5)`就可以了

## 默认参数
例子1，一个my_power函数，计算x的n次方，默认为二次方
```
def my_power(x,n=2):
	s = 1
	i = 1
	while i <= n:
		s = s * x
		i = i + 1
	return s
```

例子2，一个add函数，在一个list后面添加元素x
```
def add(L,x):
	L.append(x)
	return L	#注意return不是和def对齐的，是在def下的

```
调用函数：`add(['apple',2],1)`得到结果`['apple', 2, 1]`

**默认参数的大坑**
一下引用自廖雪峰的官方网站，https://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000/001431752945034eb82ac80a3e64b9bb4929b16eeed1eb9000

默认参数很有用，但使用不当，也会掉坑里。默认参数有个最大的坑，演示如下：
先定义一个函数，传入一个list，添加一个END再返回：

```
def add_end(L=[]):
    L.append('END')
    return L
```
当你正常调用时，结果似乎不错：
```
>>> add_end([1, 2, 3])
[1, 2, 3, 'END']
>>> add_end(['x', 'y', 'z'])
['x', 'y', 'z', 'END']
```
当你使用默认参数调用时，一开始结果也是对的：
```
>>> add_end()
['END']
```
但是，再次调用add_end()时，结果就不对了：
```
>>> add_end()
['END', 'END']
>>> add_end()
['END', 'END', 'END']
```
很多初学者很疑惑，默认参数是[]，但是函数似乎每次都“记住了”上次添加了'END'后的list。

原因解释如下：

**Python函数在定义的时候，默认参数L的值就被计算出来了，即[]，因为默认参数L也是一个变量，它指向对象[]，每次调用该函数，如果改变了L的内容，则下次调用时，默认参数的内容就变了，不再是函数定义时的[]了。所以，定义默认参数要牢记一点：默认参数必须指向不变对象！**

要修改上面的例子，我们可以用None这个不变对象来实现：
```
def add_end(L=None):
    if L is None:
        L = []
    L.append('END')
    return L
```
注意：
- 这里的`None`是不变对象，是`空`的意思，相当于C++的`null`，注意不是`none`;
- 判断，`if L is None`,注意这里用的是`is`
- L=[]说明了L的数据类型，是一个空的list，和空不同，类比C++；

现在，无论调用多少次，都不会有问题：
```
>>> add_end()
['END']
>>> add_end()
['END']
```
为什么要设计str、None这样的不变对象呢？因为不变对象一旦创建，对象内部的数据就不能修改，这样就减少了由于修改数据导致的错误。此外，由于对象不变，多任务环境下同时读取对象不需要加锁，同时读一点问题都没有。我们在编写程序时，如果可以设计一个不变对象，那就尽量设计成不变对象。

## 可变参数
传入的参数个数可变的，在参数前面加了一个*号
例子，计算a^2 + b^2 + c^2 + ……
方法一，用固定参数
```
def func(N)  # N是一个list或者tuple的类型
	s = 0
	for x in N:
		s = s + x * x
	return s
```
如果调用，必须先构造出一个list或者tuple的类型，比如`a = [1,2,3]`，比如`func(a)`，或者`func([1,2,3])`。

方法二：
```
def func1(*N):
	s = 0
	for i in N:
		s = s + i * i
	return s
```
和方法一不同的地方在于多了`*`，调用函数的方式变成了`func1(1,2,3)`,`func1(1,2,3,4,5)`，`func1()`都是可以的

如果已经有一个list或者tuple类型，要调用一个可变参数，比如`nums=[1,2,3]`，可以用`func1(nums[0], nums[1], nums[2])`或者`calc(*nums)`
表示把`nums`这个`list`的所有元素作为可变参数传进去。这种写法相当有用，而且很常见。

## 关键字参数

## 递归函数

例子，求解n!
```
def func(n):
	if n is 1:
		return 1
	else:
		return n * func(n-1)
```