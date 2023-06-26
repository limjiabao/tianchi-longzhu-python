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



