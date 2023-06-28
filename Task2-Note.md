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

1. 

## 字符串



## 字典



## 集合



## 序列



