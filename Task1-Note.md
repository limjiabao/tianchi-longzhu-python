# Task-1 Python Basics Primer:From Variables to Exception Handling



## 变量、运算符与数据类型

### 1、注释

[单行注释]

```python
# 这是一个单行注释
print("hello world!")

# hello world
```

[多行注释]

```python
'''
此处是多行注释, 行1,
此处是多行注释, 行2,
此处是多行注释, 行3,
'''

print("hello china")

"""
此处是多行注释的另一种写法,行1
此处是多行注释的另一种写法,行2
此处是多行注释的另一种写法,行3
"""
```

【我是测试题1】请在下方代码块中打印(print)出 hello+你的姓名
如：print("hello 老表")

```python
print("hello limjiabao")
```



### 2、运算符

**算数运算符**

```python
# + 加
print(1 + 2) # result = 3

# - 减
print(8 - 1) # result = 7

# * 乘
print(2 * 3) # result = 6

# / 除
print(3 / 4) # result = 0.75

# // 整除
print(3 // 4) # result = 0

# % 取余
print(3 % 4) # result = 3

# ** 幂
print(2 ** 3) # result = 8

```

**比较运算符**

```python
# > 大于
print(2 > 1) # True

# >= 大于等于
print(2 >= 14) # False

# < 小于
print(1 < 2) # True

# <= 小于等于
print(5 <= 2) # False

# == 等于
print(3 == 4) # False

# != 不等于
print(3 !=5) # True
```

**逻辑运算符**

```python
# and 与
print((3>2) and (3<5)) # True

# or 或
print((1>3) or (9<2)) # True

# not 非
print(not (2>1)) # False
```

**位运算符**

```python
print(bin(4)) # 0b100
print(bin(5)) # 0b101

# ~ 按位取返
print(bin(~4), ~4) # -0b101 -5

# & 按位与
print(bin(4 & 5), 4 & 5) # 0b100 4

# | 按位或
print(bin(4 | 5), 4 | 5) # 0b101 5

# ^ 按位异或
print(bin(4 ^ 5), 4 ^ 5) # 0b1 1

# << 左移
print(bin(4 << 2), 4 << 2) # 0b10000 16

# >> 右移
print(bin(4 >> 2), 4 >> 2) # 0b1 1
```



**三元运算符**

```python
x, y = 4, 5

if x < y:
  small = x
else:
  small = y
print(small)

# 将其使用三元操作符表达式，简化表达以上代码
x, y = 4, 5

small = x if x < y else y
print(small) # 4
```



**其他运算符**

```python
letters = ['A', 'B','C']

# in 存在, not in 不存在
if 'A' in letters:
  print('A' + 'exists')
if 'h' not in letters:
  print('h' + 'not exists')

```

```python
#【例子】比较的两个变量均指向不可变类型。
a = "hello"
b = "hello"

# is 是， is not 不是
print(a is b, a == b) # False, True
print(a is not b, a != b) # True, False

'''
1、is, not is 对比两个变量内存地址
2、==, != 对比两个变量的值
3、比较的两个变量，指向的都是地址不可变的类型（如str等）， 那么is，is not 和 ==, !=是完全等价的
4、对比的两个变量，指向的是地址可变的类型（list，dict，tuple等），则两者是存在区别的
'''
```

**运算符优先级**

```python
'''
1、** 指数， 最高优先级
2、~+- 按位翻转，一元加号和减号
3、* / % // 乘，除，取模和取整除
4、+- 加减法
5、<< >> 左移，右移
6、& 按位与
7、^| 位运算符
8、<= < > >= 比较运算符
9、<> == != 等于运算符
10、= %= /= *= //= -= += 赋值运算符
11、is , is not 身份运算符
12、in, not in 成员运算符
13、not and or 逻辑运算符
'''

print(-3 ** 2) # -9
print((-3) ** 2) # 9
print(3 ** -2) # 0.1111111111111111
print(1 << 3 + 2 & 7)  # 0
print(-3 * 2 + 5 / -2 - 4)  # -12.5
print(3 < 4 and 4 < 5)  # True
```

```python
#【我是测试题2】下面这段代码的运行结果是什么？
a = "hello"
b = "hello"
print (a is b, a == b) # True, True
```



### 3、变量

- 变量使用前，需要先对其赋值
- 变量名可以包含字母、数字、下划线、但变量名不能以数字开头
- Python是变量名大小写敏感， foo != Foo

```python
#【我是测试题3】运行下面一段代码看看结果是什么？
set_1 = {"欢迎","学习","Python"}
print(set_1.pop())  # 学习
```



### 4、数据类型与转换

**整型**

int    <class,'int'>

```python
a = 1030
print(a, type(a)) # 1030, <class 'int'>

# 整型在python中也是对象，其有对应的属性和方法
```

**浮点型**

float <class 'float'>

**布尔型**

True、False

```python
# 类型转换
print(int('520')) # 520
print(int(520.25)) # 520
print(float('520.25')) #520.25
print(str(10 + 10)) # 20
print(str(10.1 + 5.2)) # 15.3
```



**位运算**

1、原码: 就是其二进制表示（注意，有一位符号位）。

```python
00 00 00 11 -> 3
10 00 00 11 -> -3
```

2、反码：正数的反码就是原码，负数的反码是符号位不变，其余位取反（对应正数按位取反）。

```python
00 00 00 11 -> 3
11 11 11 00 -> -3
```

3、补码：正数的补码就是原码，负数的补码是反码+1。

```python
00 00 00 11 -> 3
11 11 11 01 -> -3
```

**符号位**：最高位为符号位，0表示正数，1表示负数。在位运算中符号位也参与运算。



## 条件语句

1、if 语句

```python
'''
if expression:
  expr_true_suite
'''

if 2 > 1 and not 2 > 3:
  print('Correct Judgement!')
```

2、if-else 语句

```python
'''
if expression:
  expr_true_suite
else:
  expr_true_suite
'''
temp = input("猜一猜小姐姐想的是哪个数字？")
guess = int(temp) # input 函数将接收的任何数据类型都默认为 str。
if guess == 666:
    print("你太了解小姐姐的心思了！")
    print("哼，猜对也没有奖励！")
else:
    print("猜错了，小姐姐现在心里想的是666！")
print("游戏结束，不玩儿啦！")
```

3、if - elif - else 语句

```python
'''
if expression1:
    expr1_true_suite
elif expression2:
    expr2_true_suite
    .
    .
elif expressionN:
    exprN_true_suite
else:
    expr_false_suite
'''

temp = input('请输入成绩:')
source = int(temp)
if 100 >= source >= 90:
    print('A')
elif 90 > source >= 80:
    print('B')
elif 80 > source >= 60:
    print('C')
elif 60 > source >= 0:
    print('D')
else:
    print('输入错误！')
```

4、assert 关键词

```python
my_list = ['lsgogroup']
my_list.pop(0)

assert len(my_list) > 0 # AssertionError

# 在进行单元测试时，可以用来在程序中置入检查点，只有条件为 True 才能让程序正常工作。
```

## 循环语句

1、while循环

```python
count = 0
while count < 3:
    temp = input("猜一猜小姐姐想的是哪个数字？")
    guess = int(temp)
    if guess > 8:
        print("大了，大了")
    else:
        if guess == 8:
            print("你太了解小姐姐的心思了！")
            print("哼，猜对也没有奖励！")
            count = 3
        else:
            print("小了，小了")
    count = count + 1
print("游戏结束，不玩儿啦！")
```

2、while-else 循环

```python
'''
while 布尔表达式:
    代码块
else:
    代码块
'''

count = 0
while count < 5:
    print("%d is  less than 5" % count)
    count = count + 1
else:
    print("%d is not less than 5" % count)
    
# 0 is  less than 5
# 1 is  less than 5
# 2 is  less than 5
# 3 is  less than 5
# 4 is  less than 5
# 5 is not less than 5
```

3、for 循环

```python
'''
for循环是迭代循环，在Python中相当于一个通用的序列迭代器，可以遍历任何有序序列，如str、list、tuple等，也可以遍历任何可迭代对象，如dict。

for 迭代变量 in 可迭代对象:
    代码块

'''
for i in 'ILoveLSGO':
    print(i, end=' ')  # 不换行输出

# I L o v e L S G O
```

