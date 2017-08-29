

## Variable
```
spam = 5
```
The variable `spam` now stores the number `5`.

You can use variables to store booleans like this:
```
a = True
b = False
```
**Caution:**
**`false` is not a boolen variable, but a string.**
Say `my_int = 7`. You can change the value of a variable by "reassigning" it, like this:
```
my_int = 3
```
And print it:
```
print my_int
```


## Whitespace(空白符)
```
 Python语言是一款对缩进非常敏感的语言，给很多初学者带来了困惑，即便是很有经验的python程序员，也可能陷入陷阱当中。最常见的情况是tab和空格的混用会导致错误，或者缩进不对，而这是用肉眼无法分别的。

在编译时会出现这样的错IndentationError:expected an indented block说明此处需要缩进，你只要在出现错误的那一行，按空格或Tab（但不能混用）键缩进就行。

往往有的人会疑问：我根本就没缩进怎么还是错，不对，该缩进的地方就要缩进，不缩进反而会出错，，比如：

if xxxxxx：
（空格）xxxxx

或者
def xxxxxx：
（空格）xxxxx

还有
for xxxxxx：
（空格）xxxxx

一句话 有冒号的下一行往往要缩进，该缩进就缩进
```

比如，如下代码出错：
```
def spam():
eggs = 12
return eggs
        
print spam()
```
报错信息：
```
IndentationError: expected an indented block
```
**Instructions**

Properly indent the code with four spaces before eggs on line 2 and another four before return on line 3.

You should indent your code with four spaces.

修改为：
```
def spam():
    eggs = 12
    return eggs
        
print spam()
```

## Comments
### Single Line Comments
The `#` sign is for comments. 

### Multi-Line Comments
Instead, for multi-line comments, you can include the whole block in a set of triple quotation marks:
```
"""Sipping from your cup 'til it runneth over,
Holy Grail.
"""
```

## Math
You can add, subtract, multiply, divide numbers like this
```
addition = 72 + 23
subtraction = 108 - 204
multiplication = 108 * 0.5
division = 108 / 9
```
Exponentiation: (2^3)
```
eight = 2 ** 3
```
