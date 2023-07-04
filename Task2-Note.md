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
str8 = "{0} Love {1}".format('I', 'Lsgogroup')  # 位置参数 I Love Lsgogroup

str8 = "{a} Love {b}".format(a='I', b='Lsgogroup')  # 关键字参数 I Love Lsgogroup

str8 = "{0} Love {b}".format('I', b='Lsgogroup')  # 位置参数要在关键字参数之前

str8 = '{0:.2f}{1}'.format(27.658, 'GB')  # 保留小数点后两位 I Love Lsgogroup

```



## 字典

1、字典是python中唯一的一个映射类型，字符串、元组、列表都属于序列

2、那么如何快速判断一个数据类型 `X` 是不是可变类型的呢？两种方法：

- 麻烦方法：用 `id(X)` 函数，对 X 进行某种操作，比较操作前后的 `id`，如果不一样，则 `X` 不可变，如果一样，则 `X` 可变。
- 便捷方法：用 `hash(X)`，只要不报错，证明 `X` 可被哈希，即不可变，反过来不可被哈希，即可变。

```python
i = 1
print(id(i)) # 140732167000896

i = i + 2
print(id(i))  # 140732167000960

l = [1, 2]
print(id(l))  # 4300825160
l.append('Python')
print(id(l))  # 4300825160


print(hash('Name'))  # 7047218704141848153

print(hash((1, 2, 'Python')))  # 1704535747474881831

print(hash([1, 2, 'Python']))
# TypeError: unhashable type: 'list'
```

3、 字典 是无序的 键:值（`key:value`）对集合，键必须是互不相同的（在同一个字典之内）。

- `dict` 内部存放的顺序和 `key` 放入的顺序是没有关系的。

- `dict` 查找和插入的速度极快，不会随着 `key` 的增加而增加，但是需要占用大量的内存。

  字典 定义语法为 `{元素1, 元素2, ..., 元素n}`

- 其中每一个元素是一个「键值对」-- 键:值 (`key:value`)

- 关键点是「大括号 {}」,「逗号 ,」和「冒号 :」

```python
brand = ['李宁', '耐克', '阿迪达斯']
slogan = ['一切皆有可能', 'Just do it', 'Impossible is nothing']

print('耐克的口号是:', slogan[brand.index('耐克')])  

dic = {'李宁': '一切皆有可能', '耐克': 'Just do it', '阿迪达斯': 'Impossible is nothing'}
print('耐克的口号是:', dic['耐克'])  

# 通过字符串或数值作为key来创建字典。
dic1 = {1: 'one', 2: 'two', 3: 'three'}
print(dic1)  # {1: 'one', 2: 'two', 3: 'three'}
print(dic1[1])  # one
print(dic1[4])  # KeyError: 4

dic2 = {'rice': 35, 'wheat': 101, 'corn': 67}
print(dic2)  # {'wheat': 101, 'corn': 67, 'rice': 35}
print(dic2['rice'])  # 35


# 通过元组作为key来创建字典，但一般不这样使用。(弃用)
dic = {(1, 2, 3): "Tom", "Age": 12, 3: [3, 5, 7]}
print(dic)  # {(1, 2, 3): 'Tom', 'Age': 12, 3: [3, 5, 7]}
print(type(dic))  # <class 'dict'>

# 通过构造函数dict来创建字典。
dic = dict()
dic['a'] = 1
dic['b'] = 2
dic['c'] = 3

print(dic)# {'a': 1, 'b': 2, 'c': 3}

dic['a'] = 11
print(dic)# {'a': 11, 'b': 2, 'c': 3}

dic['d'] = 4
print(dic)  # {'a': 11, 'b': 2, 'c': 3, 'd': 4}

# dict(mapping) new dictionary initialized from a mapping object's (key, value) pairs
dic1 = dict([('apple', 4139), ('peach', 4127), ('cherry', 4098)])
print(dic1)  # {'cherry': 4098, 'apple': 4139, 'peach': 4127}

dic2 = dict((('apple', 4139), ('peach', 4127), ('cherry', 4098)))
print(dic2)  # {'peach': 4127, 'cherry': 4098, 'apple': 4139}

# dict(**kwargs) -> new dictionary initialized with the name=value pairs in the keyword argument list. For example: dict(one=1, two=2)
dic = dict(name='Tom', age=10)
print(dic)  # {'name': 'Tom', 'age': 10}
print(type(dic))  # <class 'dict'>

```

4、 字典内置方法

```python
# dict.fromkeys(seq[, value]) 用于创建一个新字典，以序列 seq 中元素做字典的键，value 为字典所有键对应的初始值。
seq = ('name', 'age', 'sex')
dic1 = dict.fromkeys(seq)
print(dic1)	# {'name': None, 'age': None, 'sex': None}

dic2 = dict.fromkeys(seq, 10)
print(dic2) # {'name': 10, 'age': 10, 'sex': 10}


dic3 = dict.fromkeys(seq, ('小马', '8', '男'))
print(dic3) # {'name': ('小马', '8', '男'), 'age': ('小马', '8', '男'), 'sex': ('小马', '8', '男')}

# dict.keys()返回一个可迭代对象，可以使用 list() 来转换为列表，列表为字典中的所有键。
dic = {'Name': 'lsgogroup', 'Age': 7}
print(dic.keys())  # dict_keys(['Name', 'Age'])
lst = list(dic.keys())  # 转换为列表
print(lst)  # ['Name', 'Age']

# dict.values()返回一个迭代器，可以使用 list() 来转换为列表，列表为字典中的所有值。
dic = {'Sex': 'female', 'Age': 7, 'Name': 'Zara'}
print(dic.values())# dict_values(['female', 7, 'Zara'])
print(list(dic.values()))# [7, 'female', 'Zara']

# dict.items()以列表返回可遍历的 (键, 值) 元组数组。
dic = {'Name': 'Lsgogroup', 'Age': 7}
print(dic.items())# dict_items([('Name', 'Lsgogroup'), ('Age', 7)])
print(tuple(dic.items()))# (('Name', 'Lsgogroup'), ('Age', 7))
print(list(dic.items()))# [('Name', 'Lsgogroup'), ('Age', 7)]

# dict.get(key, default=None) 返回指定键的值，如果值不在字典中返回默认值。
dic = {'Name': 'Lsgogroup', 'Age': 27}
print("Age 值为 : %s" % dic.get('Age'))  # Age 值为 : 27
print("Sex 值为 : %s" % dic.get('Sex', "NA"))  # Sex 值为 : NA
print(dic)  # {'Name': 'Lsgogroup', 'Age': 27}	

# dict.setdefault(key, default=None)和get()方法 类似, 如果键不存在于字典中，将会添加键并将值设为默认值。
dic = {'Name': 'Lsgogroup', 'Age': 7}
print("Age 键的值为 : %s" % dic.setdefault('Age', None))  # Age 键的值为 : 7
print("Sex 键的值为 : %s" % dic.setdefault('Sex', None))  # Sex 键的值为 : None
print(dic)  # {'Age': 7, 'Name': 'Lsgogroup', 'Sex': None}

# key in dict in 操作符用于判断键是否存在于字典中，如果键在字典 dict 里返回true，否则返回false。而not in操作符刚好相反，如果键在字典 dict 里返回false，否则返回true。
dic = {'Name': 'Lsgogroup', 'Age': 7}
# in 检测键 Age 是否存在
if 'Age' in dic:
    print("键 Age 存在")
else:
    print("键 Age 不存在")

# 检测键 Sex 是否存在
if 'Sex' in dic:
    print("键 Sex 存在")
else:
    print("键 Sex 不存在")

# not in 检测键 Age 是否存在
if 'Age' not in dic:
    print("键 Age 不存在")
else:
    print("键 Age 存在")
    
# dict.pop(key[,default])删除字典给定键 key 所对应的值，返回值为被删除的值。key 值必须给出。若key不存在，则返回 default 值。
dic1 = {1: "a", 2: [1, 2]}
print(dic1.pop(1), dic1)  # a {2: [1, 2]}

# 设置默认值，必须添加，否则报错
print(dic1.pop(3, "nokey"), dic1)  # nokey {2: [1, 2]}

# del dict[key] 删除字典给定键 key 所对应的值。
del dic1[2]
print(dic1)  # {}


# dict.popitem()随机返回并删除字典中的一对键和值，如果字典已经为空，却调用了此方法，就报出KeyError异常。
dic1 = {1: "a", 2: [1, 2]}
print(dic1.popitem())  # {2: [1, 2]}
print(dic1)  # (1, 'a')

# dict.clear()用于删除字典内所有元素。
dic = {'Name': 'Zara', 'Age': 7}
print("字典长度 : %d" % len(dic))  # 字典长度 : 2
dic.clear()
print("字典删除后长度 : %d" % len(dic))  # 字典删除后长度 : 0

# dict.copy()返回一个字典的浅复制。
dic1 = {'Name': 'Lsgogroup', 'Age': 7, 'Class': 'First'}
dic2 = dic1.copy()
print("dic2")   # {'Age': 7, 'Name': 'Lsgogroup', 'Class': 'First'}


# 直接赋值和 copy 的区别
dic1 = {'user': 'lsgogroup', 'num': [1, 2, 3]}
# 引用对象
dic2 = dic1  
# 浅拷贝父对象（一级目录），子对象（二级目录）不拷贝，还是引用
dic3 = dic1.copy()  
print(id(dic1))  # 148635574728
print(id(dic2))  # 148635574728
print(id(dic3))  # 148635574344

# 修改 data 数据
dic1['user'] = 'root'
dic1['num'].remove(1)

# 输出结果
print(dic1)  # {'user': 'root', 'num': [2, 3]}
print(dic2)  # {'user': 'root', 'num': [2, 3]}
print(dic3)  # {'user': 'runoob', 'num': [2, 3]}

# dict.update(dict2)把字典参数 dict2 的 key:value对 更新到字典 dict 里。
dic = {'Name': 'Lsgogroup', 'Age': 7}
dic2 = {'Sex': 'female', 'Age': 8}
dic.update(dic2)
print(dic)  # {'Sex': 'female', 'Age': 8, 'Name': 'Lsgogroup'}
```



## 集合

1、Python 中`set`与`dict`类似，也是一组`key`的集合，但不存储`value`。由于`key`不能重复，所以，在`set`中，没有重复的`key`。`key`为不可变类型，即可哈希的值。

```python
num = {}
print(type(num))  # <class 'dict'>
num = {1, 2, 3, 4}
print(type(num))  # <class 'set'>

# 集合创建
#先创建对象再加入元素。
#在创建空集合的时候只能使用s = set()，因为s = {}创建的是空字典。
basket = set()
basket.add('apple')
basket.add('banana')
print(basket)  # {'banana', 'apple'}

# 直接把一堆元素用花括号括起来{元素1, 元素2, ..., 元素n}。
basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
print(basket)  # {'banana', 'apple', 'pear', 'orange'}

# 使用set(value)工厂函数，把列表或元组转换成集合。
a = set('abracadabra')
print(a)  # {'r', 'b', 'd', 'c', 'a'}

b = set(("Google", "Lsgogroup", "Taobao", "Taobao"))
print(b)  # {'Taobao', 'Lsgogroup', 'Google'}

c = set(["Google", "Lsgogroup", "Taobao", "Google"])
print(c)  
# {'Taobao', 'Lsgogroup', 'Google'}


# case 1 去掉列表中重复的元素
lst = [0, 1, 2, 3, 4, 5, 5, 3, 1]
temp = []
for item in lst:
    if item not in temp:
        temp.append(item)
print(temp)  # [0, 1, 2, 3, 4, 5]

# 第2中写法， 更简便
a = set(lst)
print(list(a))  # [0, 1, 2, 3, 4, 5]

```

2、 访问集合中的元素

```python
# 可以使用len()內建函数得到集合的大小。
s = set(['Google', 'Baidu', 'Taobao'])
print(len(s))  # 3

# 可以使用for把集合中的数据一个个读取出来。
s = set(['Google', 'Baidu', 'Taobao'])
for item in s:
    print(item)
    
# 可以通过in或not in判断一个元素是否在集合中已经存在
s = set(['Google', 'Baidu', 'Taobao'])
print('Taobao' in s)  # True
print('Facebook' not in s)  # True
```

3、集合内置方法

```python
# set.add(elmnt)用于给集合添加元素，如果添加的元素在集合中已存在，则不执行任何操作。
fruits = {"apple", "banana", "cherry"}
fruits.add("orange")
print(fruits)  # {'orange', 'cherry', 'banana', 'apple'}

ruits.add("apple")
print(fruits)  # {'orange', 'cherry', 'banana', 'apple'}

# set.update(set)用于修改当前集合，可以添加新的元素或集合到当前集合中，如果添加的元素在集合中已存在，则该元素只会出现一次，重复的会忽略。
x = {"apple", "banana", "cherry"}
y = {"google", "baidu", "apple"}
x.update(y)
print(x)# {'cherry', 'banana', 'apple', 'google', 'baidu'}

y.update(["lsgo", "dreamtech"])
print(y)# {'lsgo', 'baidu', 'dreamtech', 'apple', 'google'}

# set.remove(item) 用于移除集合中的指定元素。如果元素不存在，则会发生错误。
fruits = {"apple", "banana", "cherry"}
fruits.remove("banana")
print(fruits)  # {'apple', 'cherry'}

# set.discard(value) 用于移除指定的集合元素。remove() 方法在移除一个不存在的元素时会发生错误，而 discard() 方法不会。
fruits = {"apple", "banana", "cherry"}
fruits.discard("banana")
print(fruits)  # {'apple', 'cherry'}

# set.pop() 用于随机移除一个元素。
fruits = {"apple", "banana", "cherry"}
x = fruits.pop()
print(fruits)  # {'cherry', 'apple'}
print(x)  # banana


# set.intersection(set1, set2) 返回两个集合的交集。
# set1 & set2 返回两个集合的交集。
# set.intersection_update(set1, set2) 交集，在原始的集合上移除不重叠的元素。
a = set('abracadabra')
b = set('alacazam')
print(a)  # {'r', 'a', 'c', 'b', 'd'}
print(b)  # {'c', 'a', 'l', 'm', 'z'}

c = a.intersection(b)
print(c)  # {'a', 'c'}
print(a & b)  # {'c', 'a'}
print(a)  # {'a', 'r', 'c', 'b', 'd'}

a.intersection_update(b)
print(a)  # {'a', 'c'}

# set.union(set1, set2) 返回两个集合的并集。
# set1 | set2 返回两个集合的并集。
a = set('abracadabra')
b = set('alacazam')
print(a)  # {'r', 'a', 'c', 'b', 'd'}
print(b)  # {'c', 'a', 'l', 'm', 'z'}

print(a | b)  
# {'l', 'd', 'm', 'b', 'a', 'r', 'z', 'c'}

c = a.union(b)
print(c)  
# {'c', 'a', 'd', 'm', 'r', 'b', 'z', 'l'}


# set.difference(set) 返回集合的差集。
# set1 - set2 返回集合的差集。
# set.difference_update(set) 集合的差集，直接在原来的集合中移除元素，没有返回值。
a = set('abracadabra')
b = set('alacazam')
print(a)  # {'r', 'a', 'c', 'b', 'd'}
print(b)  # {'c', 'a', 'l', 'm', 'z'}

c = a.difference(b)
print(c)  # {'b', 'd', 'r'}
print(a - b)  # {'d', 'b', 'r'}

print(a)  # {'r', 'd', 'c', 'a', 'b'}
a.difference_update(b)
print(a)  # {'d', 'r', 'b'}

# set.symmetric_difference(set)返回集合的异或。
# set1 ^ set2 返回集合的异或。
# set.symmetric_difference_update(set)移除当前集合中在另外一个指定集合相同的元素，并将另外一个指定集合中不同的元素插入到当前集合中。
a = set('abracadabra')
b = set('alacazam')
print(a)  # {'r', 'a', 'c', 'b', 'd'}
print(b)  # {'c', 'a', 'l', 'm', 'z'}

c = a.symmetric_difference(b)
print(c)  # {'m', 'r', 'l', 'b', 'z', 'd'}
print(a ^ b)  # {'m', 'r', 'l', 'b', 'z', 'd'}

print(a)  # {'r', 'd', 'c', 'a', 'b'}
a.symmetric_difference_update(b)
print(a)  # {'r', 'b', 'm', 'l', 'z', 'd'}

# set.issubset(set)判断集合是不是被其他集合包含，如果是则返回 True，否则返回 False。
# set1 <= set2 判断集合是不是被其他集合包含，如果是则返回 True，否则返回 False。
x = {"a", "b", "c"}
y = {"f", "e", "d", "c", "b", "a"}
z = x.issubset(y)
print(z)  # True
print(x <= y)  # True

x = {"a", "b", "c"}
y = {"f", "e", "d", "c", "b"}
z = x.issubset(y)
print(z)  # False
print(x <= y)  # False


# set.issuperset(set)用于判断集合是不是包含其他集合，如果是则返回 True，否则返回 False。
# set1 >= set2 判断集合是不是包含其他集合，如果是则返回 True，否则返回 False。
x = {"f", "e", "d", "c", "b", "a"}
y = {"a", "b", "c"}
z = x.issuperset(y)
print(z)  # True
print(x >= y)  # True

x = {"f", "e", "d", "c", "b"}
y = {"a", "b", "c"}
z = x.issuperset(y)
print(z)  # False
print(x >= y)  # False

# set.isdisjoint(set) 用于判断两个集合是不是不相交，如果是返回 True，否则返回 False。
x = {"f", "e", "d", "c", "b"}
y = {"a", "b", "c"}
z = x.isdisjoint(y)
print(z)  # False

x = {"f", "e", "d", "m", "g"}
y = {"a", "b", "c"}
z = x.isdisjoint(y)
print(z)  # True
```

4、 集合转换

```python
# case 1
se = set(range(4))
li = list(se)
tu = tuple(se)

print(se, type(se))  # {0, 1, 2, 3} <class 'set'>
print(li, type(li))  # [0, 1, 2, 3] <class 'list'>
print(tu, type(tu))  # (0, 1, 2, 3) <class 'tuple'>
```

5、不可变集合

```python
# frozenset([iterable]) 返回一个冻结的集合，冻结后集合不能再添加或删除任何元素。
a = frozenset(range(10))  # 生成一个新的不可变集合
print(a)    # frozenset({0, 1, 2, 3, 4, 5, 6, 7, 8, 9})

b = frozenset('lsgogroup')
print(b)  # frozenset({'g', 's', 'p', 'r', 'u', 'o', 'l'})
```



## 序列

1、

