
## 输入
input() 
比如：
```
name = input()
```
于是接下来会等待你的输入，赋值给name

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

# 字符编码

- ASCII编码：一个字节（8bits），127个，有一位奇偶校验
- Unicode：最常用的是用两个字节表示一个字符。最新的Python 3版本中，字符串是以Unicode编码。

- 为了节约字符，有一种可变长的编码 UTF-8，英文字符一个字节，汉字三个字节。
- 在计算机内存中，统一使用**Unicode编码**，当需要保存到硬盘或者需要传输的时候，就转换为**UTF-8编码**。

<img src="./images/记事本编辑.png"/>




