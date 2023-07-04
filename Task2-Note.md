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

# case 4
```



## 字典

1、

## 集合

1、

## 序列

1、

