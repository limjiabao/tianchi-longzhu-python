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

  

- 关键字参数

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

- 命名关键字参数

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



- 组合参数

```python
'''
Python 中定义函数，可以用位置参数、默认参数、可变参数、命名关键字参数和关键字参数，这 5 种参数中的 4 个都可以一起使用，但是注意，参数定义的顺序必须是：

位置参数、默认参数、可变参数和关键字参数。
位置参数、默认参数、命名关键字参数和关键字参数。
要注意定义可变参数和关键字参数的语法：

*args 是可变参数，args 接收的是一个 tuple
**kw 是关键字参数，kw 接收的是一个 dict
命名关键字参数是为了限制调用者可以传入的参数名，同时可以提供默认值。定义命名关键字参数不要忘了写分隔符 *，否则定义的是位置参数。

警告：虽然可以组合多达 5 种参数，但不要同时使用太多的组合，否则函数很难懂。
'''
```

4、函数返回值

```python
#Case1
def add(a, b):
    return a + b
  
print(add(1, 2))  # 3
print(add([1, 2, 3], [4, 5, 6]))  # [1, 2, 3, 4, 5, 6]


#Case2
def back():
  return [1, 'limjiabao', 3.14]


print(back())  # [1, 'limjiabao', 3.14]


#Case3
def back():
    return 1, 'limjiabao', 3.14

print(back())  # (1, '小马的程序人生', 3.14)

# Case4
def printme(str):
    print(str)
    
temp = printme('hello') # hello
print(temp) # None
print(type(temp))  # <class 'NoneType'>
```

5、变量作用域

- 定义在函数内部的变量拥有局部作用域，该变量称为局部变量。
- 定义在函数外部的变量拥有全局作用域，该变量称为全局变量。
- 局部变量只能在其被声明的函数内部访问，而全局变量可以在整个程序范围内访问。

```python
# Case 1
def discounts(price,rate):
  	final_price = price * rate
    return final_price
  
old_price = float(input('请输入原价:'))  # 98
rate = float(input('请输入折扣率:'))  # 0.9
new_price = discounts(old_price, rate)
print('打折后价格是:%.2f' % new_price)  # 88.20
```

```python
# Case 2
# 当内部作用域想修改外部作用域的变量时，就要用到global和nonlocal关键字了。
num = 1

def fun1():
  global num # 需要使用 global 关键字声明
  print(num) # 1
  num = 123
  print(num) # 123
  
fun1()
print(num) # 123
```

6、内嵌函数

```python
# Case 1
def outer():
  print("outer 函数在这里被调用")
  
  def inner():
    print('inner 函数在这被调用')
    
  inner()

  
outer()
# outer函数在这被调用
# inner函数在这被调用
```

7、闭包

- 函数式编程的重要语法结构，特殊的内嵌函数
- 如果在一个内部函数里对外层非全局作用域的变量进行引用，那么内部函数就被认为是闭包
- 通过闭包可以访问外层非全局作用域的变量，这个作用域成为闭包作用域

```python
# Case 1
def funX(x):
  
  def funY(y):
    return x * y
  
 	return funY

i = funX(8)
print(type(i)) 	# <class 'function'>
print(i(5))  		# 40
```

- 闭包的返回值通常是函数

```python
def make_counter(init)；
		counter = [init]
  
  	def inc():
      counter[0] += 1
    
    def dec():
      counter[0] -= 1
      
    def get():
      return counter[0]
    
    def reset():
      counter[0] = init
      
  	return inc,dec,get,reset
  
  
inc,dec,get,reset = make_counter(0)

inc()
inc()
inc()

print(get())  # 3

dec()
print(get()) # 2

reset()
print(get()) # 0
```

- 如果要修改闭包作用域中的变量则需要 `nonlocal` 关键字

  ```python
  # Case
  def outer():
    num = 10
    
    def inner():
      nonlocal num # nonlocal关键字声明
      num = 100
      print(num)
    
    inner()
    print(num)
  
  outer() 
  # 100
  # 100
  ```

  8、递归

  - 如果一个函数在内部调用自身本身，这个函数就是递归函数

  ```python
  # 阶乘 n! = 1 * 2 * 3 * ... * n
  
  # Case 1 循环模式
  n = 5
  for k in range(1,5):
    n = n * k
  print(n)  # 120
  
  # Case 2 递归模式
  
  def factorial(n):
    if n == 1:
      return 1
    return n * factorial(n-1)
  
  print(factorial(5)) # 120
  
  
  # 斐波那契数列 f(n)=f(n-1)+f(n-2), f(0)=0 f(1)=1
  
  # Case 3 循环模式
  i = 0
  j = 1
  lst = list([i,j])
  
  for k in range(2,11):
    	k = i + j
      lst.append(k)
      i = j
      j = k
   
  print(lst) # [0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55]
  
  
  # Case 4 递归模式
  def recur_fibo(n):
    	if n <= 1:
         return n
      return recur_fibo(n - 1) + recur_fibo(n - 2)
  
  lst = list()
  
  for k in range(11):
    lst.append(recur_fibo(k))
  print(lst)    # [0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55]
  ```

  ```python
  # 设置递归的层数，python默认递归层数为100
  import sys
  
  sys.setrecursionlimit(1000)
  ```

  9、lambda 表达式

  - lambda关键词定义的函数是匿名函数，属于python定义函数的一种

  ```python
  # Case 1 普通函数
  def sqr(x):
    return x ** 2
  
  print(sqr)# <function sqr at 0x000000BABD3A4400>
  
  
  y = [sqr(x) for x in range(10)]
  print(y)# [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
  
  # Case 2 lambda
  lbd_sqr = lambda x:x**2
  print(lbd_sqr) # <function <lambda> at 0x000000BABB6AC1E0>
  
  y = [lbd_sqr(x) for x in range(10)]
  print(y)	# [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
  
  # Case 3 lambda
  sumary = lambda arg1, arg2: arg1 + arg2
  print(sumary(10, 20))  # 30
  
  # Case 4 lambda 可变参数
  func = lambda *args: sum(args)
  print(func(1, 2, 3, 4, 5))  # 15
  ```

  ## 类与对象

  1、类定义

  ```python
  class Turtle:
    """关于类的一个简单例子"""
    # 属性
    color = 'green'
    weight = 10
    legs = 4
    shell = True
    mouth = '大嘴'
    
    # method
    def climb(self):
        print('我正在很努力的向前爬...')
  
    def run(self):
        print('我正在飞快的向前跑...')
  
    def bite(self):
        print('咬死你咬死你!!')
  
    def eat(self):
        print('有得吃，真满足...')
  
    def sleep(self):
        print('困了，睡了，晚安，zzz')	
        
        
        
  tt = Turtle()
  print(tt)   		# <__main__.Turtle object at 0x0000007C32D67F98>
  
  print(type(tt)) # <class '__main__.Turtle'>
  
  print(tt.__class__) # <class '__main__.Turtle'>
  
  print(tt.__class__.__name__) # Turtle
  
  tt.climb()  # 我正在很努力的向前爬...
  
  tt.run()   # 我正在飞快的向前跑...
  
  tt.bite()	 # 咬死你咬死你!!
  
  # Python类也是对象。它们是type的实例
  print(type(Turtle)) # <class 'type'>
  ```

2、继承

```python
class MyList(list):
			pass
  
lst = MyList([1, 5, 2, 7, 8])
lst.append(9)
lst.sort()
print(lst)
```

3、多态

- 不同对象对同一方法响应不同的行动

  ```python
  class Animal:
    def run(self):
      raise AttributeError('子类必须实现这个方法')
      
  
  class People(Animal):
    def run(self):
      print('人正在走')
      
   
  class Pig(Animal):
    def run(self):
      print('pig is walking')
      
  class Dog(Animal):
    def run(self):
      print('dog is running')
      
      
   def func(animal):
    	animal.run()
      
   func(Pig())  # pig is walking
  ```

  ```python
  """
  	Python 中的self相当于C++的this指针
  """
  
  class Test:
    def prt(self):
      print(self)
      print(self.__class__)
      
      
  t = Test()
  t.prt() 
  # <__main__.Test object at 0x000000BC5A351208>
  # <class '__main__.Test'>
  
  """
  	类的方法与普通的函数只有一个特别的区别 —— 它们必须有一个额外的第一个参数名称（对应于该实例，即该对象本身），按照惯例它的名称是 self。在调用方法时，我们无需明确提供与参数 self 相对应的参数。
  """
  
  # Case 1
  class Ball:
    def setName(self, name):
      self.name = name
      
    def kick(self):
      print("我叫%s,该死的，谁踢我..." % self.name)
      
  a = Ball()
  a.setName("球A")
  b = Ball()
  b.setName("球B")
  c = Ball()
  c.setName("球C")
  a.kick()
  # 我叫球A,该死的，谁踢我...
  b.kick()
  # 我叫球B,该死的，谁踢我...
  ```

  

  3、公有、私有

  ```python
  class JustCounter:
    __secretCount = 0  # 私有变量
    publicCount = 0  # 公开变量
    
    def count(self):
      self.__secretCount += 1
      self.publicCount += 1
      print(self.__secretCount)
  
  counter = JustCounter()
  counter.count()  # 1
  counter.count()  # 2
  print(counter.publicCount)  # 2
  
  
  # Python的私有为伪私有
  print(counter._JustCounter__secretCount)  # 2
  print(counter.__secretCount)  # AttributeError: 'JustCounter' object has no attribute '__secretCount'
  
  
  # 类的私有方法实例 Case
  class Site:
    def __init__(self, name, url):
      self.name = name  # public
      self.__url = url  # private
    
    
    def who(self):
      print('name  : ', self.name)
      print('url : ', self.__url)
      
    def __foo(self):  # 私有方法
      print('这是私有方法')
      
    def foo(self):  # 公共方法
      print('这是公共方法')
      self.__foo()
      
  x = Site('limjiabao', 'https://blog.csdn.net/limjiabao')
  x.who()  
  # name  :  老马的程序人生
  # url :  https://blog.csdn.net/LSGO_MYP
  
  x.foo()
  # 这是公共方法
  # 这是私有方法
  
  
  x.__foo()
  # AttributeError: 'Site' object has no attribute '__foo'
  ```

  

  ## 魔法方法

  - 魔法方法总是被双下划线包围，例如`__init__`。
  - 魔法方法是面向对象的 Python 的一切，如果你不知道魔法方法，说明你还没能意识到面向对象的 Python 的强大。
  - 魔法方法的“魔力”体现在它们总能够在适当的时候被自动调用。
  - 魔法方法的第一个参数应为`cls`（类方法） 或者`self`（实例方法）。
  - 若`__new__`没有正确返回当前类`cls`的实例，那`__init__`是不会被调用的，即使是父类的实例也不行，将没有`__init__`被调用。

  ```python
  '''
  __init__(self[, param1, param2...])  该方法在类实例化时会自动调用
  '''
  
  class Ball:
      def __init__(self, name):
          self.name = name
          
       def kick(self):
          print("我叫%s,该死的，谁踢我..." % self.name)
  
  a = Ball("球A")
  b = Ball("球B")
  c = Ball("球C")
  a.kick()  # 我叫球A,该死的，谁踢我...
  
  b.kick()  # 我叫球B,该死的，谁踢我...
  
  
  '''
  __new__(cls[,...]) 在一个对象实例化的时候所调用的第一个方法，在调用__init__初始化前，先调用__new__
  '''
  
  class A(object):
    def __init__(self,value):
      print("into A __init__")
      self.value = value
      
    def __new__(cls,*args,**kwargs):
      print("into A __new__")
      print(cls)
      return object.__new__(cls)
    
  
  class B(A):
    def __init__(self,value):
      print("into B __init__")
      self.value = value
      
    def __new__(cls,*args,**kwargs):
      print("into B __new__")
      print(cls)
      return super().__new__(cls,*args,**kwargs)
    
  b = B(10)
  # 结果：
  # into B __new__
  # <class '__main__.B'>
  # into A __new__
  # <class '__main__.B'>
  # into B __init__
  ```

  ```python
  # Case 利用__new__实现单例模式。
  class earth:
    pass
  
  a = Earth()
  print(id(a))  # 260728291456
  b = Earth()
  print(id(b))  # 260728291624
  
  
  class Earth:
      __instance = None  # 定义一个类属性做判断
      
      
      def __new__(cls):
        if cls.__instance is None:
           cls.__instance = object.__new__(cls)
           return cls.__instance 
        else:
          return cls.__instance
        
   
  a = Earth()
  print(id(a))  # 512320401648
  b = Earth()
  print(id(b))  # 512320401648
  
  
  ```

  ## 生成器

  ```python
  def libs(n):
    a = 0
    b = 1
    while True:
      a, b = b, a + b
      if a > n:
        return
      yield a
      
  for each in libs(100):
    print(each, end = ' ')
    
  # 1 1 2 3 5 8 13 21 34 55 89
  ```

  

  

