# Task- 3 Getting Started with Python (below)

## 函数

1、函数定义

```python
'''
def functionname(parameters):
  "函数文档字符串"
  functionsuite
  return [expression]

# return [表达式] 结束函数，选择性地返回一个值给调用方。不带表达式的return相当于返回None
'''
```

```python
# Case 1
def printme(str):
  print(str)

printme("我要调用用户自定义函数!")  # 我要调用用户自定义函数!
printme("再次调用同一函数")  # 再次调用同一函数
temp = printme('hello') # hello
print(temp)  # None
```

2、函数文档

```python
def MyFirstFunction(name):
  "函数定义过程中name是形参"
   # 因为Ta只是一个形式，表示占据一个参数位置
   print('传递进来的{0}叫做实参，因为Ta是具体的参数值！'.format(name))
  
MyFirstFunction('limjiabao的程序人生')  # 传递进来的"limjiabao的程序人生"叫做实参，因为Ta是具体的参数值！

print(MyFirstFunction.__doc__)  
# 函数定义过程中name是形参

help(MyFirstFunction)
# Help on function MyFirstFunction in module __main__:
# MyFirstFunction(name)
#    函数定义过程中name是形参
```

3、函数参数

- 位置参数

  ```python
  '''
  def functionname(arg1):
  		"函数文档字符串"
  		functionsuite
      return [expression]
      
   # arg1 - 位置参数，这些参数在调用函数(call function)时位置要固定
  '''
  ```

- 默认参数

  ```python
  # Case
  def functionname(name, age=8):
  	print('Name:{0}, Age:{1}'.format(name,age))
  
   printinfo('小马')  # Name:小马,Age:8
  printinfo('小马', 10)  # Name:小马,Age:10
  
  # python 允许函数调用时参数的顺序与声明时不一致，python解释器能够用参数名匹配参数值
  def functionname(name, age):
    print('Name:{0},Age:{1}'.format(name, age))
    
  printinfo(age=8, name='小马')  # Name:小马,Age:8
  ```

- 可变参数

  ```python
  # 传入的参数个数是可变的，可以是0,1,2到任意个，不定长参数
  '''
  def functionname(arg1,arg2=v,*args):
  		 "函数文档字符串"
  		 functionsuite
  		 return [expression]
  		 
  # *args 可变参数，可从0到任意个，自动组装成元组，其会存放所有未命名的变量参数。
  '''
  
  # Case
  def printinfo(arg1,*args):
    print(arg1)
    for var in args:
      print(var)
      
  printinfo(10)  # 10
  printinfo(70, 60, 50) 
  # 70
  # 60
  # 50
  ```

  

4、关键字参数

(1) 可变参数允许传入0到任意个参数， 它们在函数调用时自动组装成元组（tuple）

(2) 关键字参数允许传入0到任意个参数，它们在函数调用时自动组装为一个字典（dict）

```python
'''
def functionname(arg1, arg2=v, *args, **kw):
		"函数文档字符串"
		functionsuite
		return [expression]
		
**kw - 关键字参数，可以是从零个到任意个，自动组装成字典。
'''

# Case
def prininfo(arg1,*args,**kwargs):
  print(arg1)
  print(args)
  print(kwargs)
  
printinfo(70, 60, 50)
# 70
# (60, 50)
# {}


printinfo(70, 60, 50, a=1, b=2)
# 70
# (60, 50)
# {'a': 1, 'b': 2}
```

5、命名关键字参数

```python
'''
def functionname(arg1,arg2=v,*args,*,nkw,**kw):
		"函数文档字符串"
     functionsuite
     return [expression]
'''

# Case
def printinfo(arg1, *, nkw, **kwargs):
  print(arg1)
  print(nkw)
  print(kwargs)
  
printinfo(70, nkw=10, a=1, b=2)
# 70
# 10
# {'a': 1, 'b': 2}

printinfo(70, 10, a=1, b=2)
# TypeError: printinfo() takes 1 positional argument but 2 were given
```

