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

4、for - else 循环

```python
'''
for 迭代变量 in 可迭代对象:
    代码块
else:
    代码块
'''

for num in range(10, 20):  # 迭代 10 到 20 之间的数字
    for i in range(2, num):  # 根据因子迭代
        if num % i == 0:  # 确定第一个因子
            j = num / i  # 计算第二个因子
            print('%d 等于 %d * %d' % (num, i, j))
            break  # 跳出当前循环
    else:  # 循环的 else 部分
        print(num, '是一个质数')

# 10 等于 2 * 5
# 11 是一个质数
# 12 等于 2 * 6
# 13 是一个质数
# 14 等于 2 * 7
# 15 等于 3 * 5
# 16 等于 2 * 8
# 17 是一个质数
# 18 等于 2 * 9
# 19 是一个质数
```

5、range() 函数

```python
# range([start,] stop[, step=1])
for i in range(1, 10, 2):
    print(i)
```

6、enumerate()函数

```python
# enumerate(sequence, [start=0])
seasons = ['Spring', 'Summer', 'Fall', 'Winter']
lst = list(enumerate(seasons))
print(lst)
# [(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]
lst = list(enumerate(seasons, start=1))  # 下标从 1 开始
print(lst)
# [(1, 'Spring'), (2, 'Summer'), (3, 'Fall'), (4, 'Winter')]
```

7、break 语句

```python
# break 语句可以跳出当前所在层的循环。
import random
secret = random.randint(1, 10) #[1,10]之间的随机数

while True:
    temp = input("猜一猜小姐姐想的是哪个数字？")
    guess = int(temp)
    if guess > secret:
        print("大了，大了")
    else:
        if guess == secret:
            print("你太了解小姐姐的心思了！")
            print("哼，猜对也没有奖励！")
            break
        else:
            print("小了，小了")
print("游戏结束，不玩儿啦！")
```

8、continue 语句

```python
# continue终止本轮循环并开始下一轮循环。
for i in range(10):
    if i % 2 != 0:
        print(i)
        continue
    i += 2
    print(i)
```

9、pass 语句

```python
# pass 语句的意思是“不做任何事”
def a_func():
    pass
```

10、推导式

```python
# [ expr for value in collection [if condition] ]
x = [-4, -2, 0, 2, 4]
y = [a * 2 for a in x]
print(y)
# [-8, -4, 0, 4, 8]
```

**元组推导式**

```python
# ( expr for value in collection [if condition] )
a = (x for x in range(10))
print(a)

# <generator object <genexpr> at 0x0000025BE511CC48>

print(tuple(a))

# (0, 1, 2, 3, 4, 5, 6, 7, 8, 9)
```

**字典推导式**

```python
# { key_expr: value_expr for value in collection [if condition] }
b = {i: i % 2 == 0 for i in range(10) if i % 3 == 0}
print(b)
# {0: True, 3: False, 6: True, 9: False}
```

**集合推导式**

```python
# { expr for value in collection [if condition] }
c = {i for i in [1, 2, 3, 4, 5, 5, 6, 4, 3, 2, 1]}
print(c)
# {1, 2, 3, 4, 5, 6}
```

**其它**

```python
# next(iterator[, default]) Return the next item from the iterator. If default is given and the iterator is exhausted, it is returned instead of raising StopIteration.

e = (i for i in range(10))
print(e)
# <generator object <genexpr> at 0x0000007A0B8D01B0>

print(next(e))  # 0
print(next(e))  # 1

for each in e:
    print(each, end=' ')

# 2 3 4 5 6 7 8 9
```

## 异常处理

1、**标准异常**

- BaseException：所有异常的 **基类**
- Exception：常规异常的 **基类**
- StandardError：所有的内建标准异常的基类
- ArithmeticError：所有数值计算异常的基类
- FloatingPointError：浮点计算异常
- OverflowError：数值运算超出最大限制
- ZeroDivisionError：除数为零
- AssertionError：断言语句（assert）失败
- AttributeError：尝试访问未知的对象属性
- EOFError：没有内建输入，到达EOF标记
- EnvironmentError：操作系统异常的基类
- IOError：输入/输出操作失败
- OSError：操作系统产生的异常（例如打开一个不存在的文件）
- WindowsError：系统调用失败
- ImportError：导入模块失败的时候
- KeyboardInterrupt：用户中断执行
- LookupError：无效数据查询的基类
- IndexError：索引超出序列的范围
- KeyError：字典中查找一个不存在的关键字
- MemoryError：内存溢出（可通过删除对象释放内存）
- NameError：尝试访问一个不存在的变量
- UnboundLocalError：访问未初始化的本地变量
- ReferenceError：弱引用试图访问已经垃圾回收了的对象
- RuntimeError：一般的运行时异常
- NotImplementedError：尚未实现的方法
- SyntaxError：语法错误导致的异常
- IndentationError：缩进错误导致的异常
- TabError：Tab和空格混用
- SystemError：一般的解释器系统异常
- TypeError：不同类型间的无效操作
- ValueError：传入无效的参数
- UnicodeError：Unicode相关的异常
- UnicodeDecodeError：Unicode解码时的异常
- UnicodeEncodeError：Unicode编码错误导致的异常
- UnicodeTranslateError：Unicode转换错误导致的异常

2、**Python标准警告总结**

- Warning：警告的基类
- DeprecationWarning：关于被弃用的特征的警告
- FutureWarning：关于构造将来语义会有改变的警告
- UserWarning：用户代码生成的警告
- PendingDeprecationWarning：关于特性将会被废弃的警告
- RuntimeWarning：可疑的运行时行为(runtime behavior)的警告
- SyntaxWarning：可疑语法的警告
- ImportWarning：用于在导入模块过程中触发的警告
- UnicodeWarning：与Unicode相关的警告
- BytesWarning：与字节或字节码相关的警告
- ResourceWarning：与资源使用相关的警告

3、**try - except 语句**

```python
'''
try:
    检测范围
except Exception[as reason]:
    出现异常后的处理代码

'''

try:
    f = open('test.txt')
    print(f.read())
    f.close()
except OSError:
    print('打开文件出错')

# 打开文件出错
```

4、try - except - finally 语句

try: 检测范围 except Exception[as reason]: 出现异常后的处理代码 finally: 无论如何都会被执行的代码

```python
def divide(x, y):
    try:
        result = x / y
        print("result is", result)
    except ZeroDivisionError:
        print("division by zero!")
    finally:
        print("executing finally clause")


divide(2, 1)
# result is 2.0
# executing finally clause
divide(2, 0)
# division by zero!
# executing finally clause
divide("2", "1")
# executing finally clause
# TypeError: unsupported operand type(s) for /: 'str' and 'str'
```

5、try - except - else 语句

```python
try:
    fh = open("testfile.txt", "w")
    fh.write("这是一个测试文件，用于测试异常!!")
except IOError:
    print("Error: 没有找到文件或读取文件失败")
else:
    print("内容写入文件成功")
    fh.close()

# 内容写入文件成功
```



6、raise语句

```python
try:
    raise NameError('HiThere')
except NameError:
    print('An exception flew by!')
    
# An exception flew by!
```

