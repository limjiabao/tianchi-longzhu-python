# Task-2 Python Fundamentals Exercise: The Big Summary of Data Structures

## 列表

1. 列表是有序集合，没有固定大小、能够保存任意数量、任意类型的Python对象

   - 以中括号包含所有元素，以逗号间隔区分元素
   - list 中所保存的是对象的指针
   - list 内容可更改
   - list.append() 将参数作为一个整体进行追加，list.extend(seq) 在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表）

   ```python
   # 普通列表创建
   x1 = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday']
   
   x2 = [2, 3, 4, 5, 6, 7]
   
   # 利用range()创建列表
   x3 = list(range(10)) # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9] 
   
   x4 = list(range(1,11,2)) # [1, 3, 5, 7, 9]
   
   x5 = list(range(10,1,-2)) # [10, 8, 6, 4, 2]
   
   # 利用推导式创建列表
   x6 = [0] * 5 # [0,0,0,0,0]
   
   x7 = [0 for i in range(5)] # [0, 0, 0, 0, 0] 
   
   x8 = [i for i in range(1,10,2)] # [1,3,5,7,9]
   
   x9 = [i**2 for i in range(1,10)] # [1, 4, 9, 16, 25, 36, 49, 64, 81] 
   
   # 删除列表列表中的元素
   x10 = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday']
   x.remove('Monday')
   ```

   

## 元组

1. 元组与list类似,区别在于元组被创建后不能修改，与字符串类似
2. 元组使用小括号
3. 元组也可以进行所以和切片

```python
t1 = (1, 10.31, 'python')
t2 = 1, 10.31, 'python'

tuple1 = (1, 2, 3, 4, 5, 6, 7, 8)
print(tuple1[1])  # 2
print(tuple1[5:])  # (6, 7, 8)
print(tuple1[:5])  # (1, 2, 3, 4, 5)
tuple2 = tuple1[:]
print(tuple2)  # (1, 2, 3, 4, 5, 6, 7, 8)

# 二维数组
x = (1, 10.31, 'python'), ('data', 11)
print(x)
# ((1, 10.31, 'python'), ('data', 11))
print(x[0])
# (1, 10.31, 'python')
print(x[0][0], x[0][1], x[0][2])
# 1 10.31 python
print(x[0][0:2])
# (1, 10.31)

# 更新和删除元组
week = ('Monday', 'Tuesday', 'Thursday', 'Friday')
week = week[:2] + ('Wednesday',) + week[2:]  
print(week)  # ('Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday')

# 元组相关的操作符
t1 = (123, 456)
t2 = (456, 123)
t3 = (123, 456)

print(t1 == t2)  # False
print(t1 == t3)  # True

t4 = t1 + t2
print(t4)  # (123, 456, 456, 123)

t5 = t3 * 3
print(t5)  # (123, 456, 123, 456, 123, 456)

t3 *= 3
print(t3)  # (123, 456, 123, 456, 123, 456)

print(123 in t3)  # True
print(456 not in t3)  # False


```



## 字符串

1、字符串被定义为引号之间的字符集合，支持使用成对的单引号或双引号。

```python
# case 1
t1 = 'I love you!'

# case 2
t2 = "I love you!"

print(5+8) # 13
print('5'+'8') # 58

# 字符串转义字符
'''
\\ 反斜杠符号
\' 单引号
\" 双引号
\n 换行
\t 横向制表符
\r 回车
'''
print('let\'s go')  # let's go
print("let's go")  # let's go
print('C:\\now')  # C:\now
print("C:\\Program Files\\Intel\\Wifi\\Help") # C:\Program Files\Intel\Wifi\Help


# case 3 原始字符串只需要在字符串前边加一个英文字母 r 即可。
print(r'C:\Program Files\Intel\Wifi\Help')  # C:\Program Files\Intel\Wifi\Help

# case 4 三引号允许一个字符串跨多行，字符串中可以包含换行符、制表符以及其他特殊字符。
para_str = """这是一个多行字符串的实例
多行字符串可以使用制表符
TAB ( \t )。
也可以使用换行符 [ \n ]。
"""
print(para_str)

```

2、字符串的切片与拼接

- 类似元组具有不可修改性
- 下标从0开始
- 切片形式 start:end 包括start对应元素，不包括end对应元素
- 索引值可正可负，正索引从0开始，从左往右，负索引从-1开始，从右往左，使用负索引会从最后一个元素开始计数，最后一个元素的位置编号是-1

```python
# case 1
str1 = 'I Love LsgoGroup'
print(str1[:6])  # I Love
print(str1[5])  # e
print(str1[:6] + " 插入的字符串 " + str1[6:])  # I Love 插入的字符串  LsgoGroup

s = 'Python'
print(s)  # Python
print(s[2:4])  # th
print(s[-5:-2])  # yth
print(s[2])  # t
print(s[-1])  # n
```

3、字符串内置方法

```python
# capitalize() 将字符串第一个字符转为大写
str1 = 'limjiabao'
print(capitalize(str1)) # Limjiabao

# lower() 将字符串所有大写字符转为小写
str2 = 'LimJiabao'
print(lower(str2)) # limjiabao

# upper() 将字符串所有小写字母转为大写
str3 = 'limjiaBao'
print(upper(str3)) # LIMJIABAO

# swapcase() 将字符串中大写转换为小写，小写转换为大写
str4 = "LimJiabao"
print(swapcase(str4)) # lIMjIABAO

# count(str, beg= 0,end=len(string)) 返回str在 string 里面出现的次数，如果beg或者end指定则返回指定范围内str出现的次数。

str5 = "DAXIExiaoxie"
print(str2.count('xi'))  # 2

# endswith(suffix, beg=0, end=len(string)) 检查字符串是否以指定子字符串 suffix 结束，如果是，返回 True，否则返回 False。如果 beg 和 end 指定值，则在指定范围内检查。
str2 = "DAXIExiaoxie"
print(str2.endswith('ie'))  # True
print(str2.endswith('xi'))  # False

# startswith(substr, beg=0,end=len(string)) 检查字符串是否以指定子字符串 substr 开头，如果是，返回 True，否则返回 False。如果 beg 和 end 指定值，则在指定范围内检查。
print(str2.startswith('DA'))  # True
print(str2.startswith('Da'))  # False

# find(str, beg=0, end=len(string)) 检测 str 是否包含在字符串中，如果指定范围 beg 和 end，则检查是否包含在指定范围内，如果包含，返回开始的索引值，否则返回 -1。
str2 = "DAXIExiaoxie"
print(str2.find('xi'))  # 5
print(str2.find('ix'))  # -1

# rfind(str, beg=0,end=len(string)) 类似于 find() 函数，不过是从右边开始查找。
print(str2.rfind('xi'))  # 9

# isnumeric() 如果字符串中只包含数字字符，则返回 True，否则返回 False。
str3 = '12345'
print(str3.isnumeric())  # True
str3 += 'a'
print(str3.isnumeric())  # False

# ljust(width[, fillchar])返回一个原字符串左对齐，并使用fillchar（默认空格）填充至长度width的新字符串。
# rjust(width[, fillchar])返回一个原字符串右对齐，并使用fillchar（默认空格）填充至长度width的新字符串。
str4 = '1101'
print(str4.ljust(8, '0'))  # 11010000
print(str4.rjust(8, '0'))  # 00001101

# lstrip([chars]) 截掉字符串左边的空格或指定字符。
# rstrip([chars]) 删除字符串末尾的空格或指定字符。
# strip([chars]) 在字符串上执行lstrip()和rstrip()。
str5 = ' I Love LsgoGroup '
print(str5.lstrip())  # 'I Love LsgoGroup '
print(str5.lstrip().strip('I'))  # ' Love LsgoGroup '
print(str5.rstrip())  # ' I Love LsgoGroup'
print(str5.strip())  # 'I Love LsgoGroup'
print(str5.strip().strip('p'))  # 'I Love LsgoGrou'


# partition(sub) 找到子字符串sub，把字符串分为一个三元组(pre_sub,sub,fol_sub)，如果字符串中不包含sub则返回('原字符串','','')。
# rpartition(sub)类似于partition()方法，不过是从右边开始查找。
str5 = ' I Love LsgoGroup '
print(str5.strip().partition('o'))  # ('I L', 'o', 've LsgoGroup')
print(str5.strip().partition('m'))  # ('I Love LsgoGroup', '', '')
print(str5.strip().rpartition('o'))  # ('I Love LsgoGr', 'o', 'up')

# replace(old, new [, max]) 把 将字符串中的old替换成new，如果max指定，则替换不超过max次。
str5 = ' I Love LsgoGroup '
print(str5.strip().replace('I', 'We'))  # We Love LsgoGroup

# split(str="", num) 不带参数默认是以空格为分隔符切片字符串，如果num参数有设置，则仅分隔num个子字符串，返回切片后的子字符串拼接的列表。
str5 = ' I Love LsgoGroup '
print(str5.strip().split())  # ['I', 'Love', 'LsgoGroup']
print(str5.strip().split('o'))  # ['I L', 've Lsg', 'Gr', 'up']

# splitlines([keepends]) 按照行('\r', '\r\n', \n')分隔，返回一个包含各行作为元素的列表，如果参数keepends为 False，不包含换行符，如果为 True，则保留换行符。
str6 = 'I \n Love \n LsgoGroup'
print(str6.splitlines())  # ['I ', ' Love ', ' LsgoGroup']
print(str6.splitlines(True))  # ['I \n', ' Love \n', ' LsgoGroup']

# maketrans(intab, outtab) 创建字符映射的转换表，第一个参数是字符串，表示需要转换的字符，第二个参数也是字符串表示转换的目标。
str7 = 'this is string example....wow!!!'
intab = 'aeiou'
outtab = '12345'

trantab = str7.maketrans(intab, outtab)
print(trantab)  # {97: 49, 111: 52, 117: 53, 101: 50, 105: 51}

```

4、 字符串格式化

```python
# format 函数
str8 = "{0} Love {1}".format('I', 'Lsgogroup')  # 位置参数

str8 = "{a} Love {b}".format(a='I', b='Lsgogroup')  # 关键字参数

str8 = "{0} Love {b}".format('I', b='Lsgogroup')  # 位置参数要在关键字参数之前
```



## 字典

1、

## 集合

1、

## 序列

1、

