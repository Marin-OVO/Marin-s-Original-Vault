---
date: 2026-09-13
tags:
  - 计算机程序的结构与解释
  - Python
---
# Lecture 1 表达式
# Lecture 2 函数
# Lecture 3
# Lecture 4 
在函数被调用以前所有部分都要被评估 
```python
## false时打印后面语句
assert r > 0, 'A length must be positive.'
```

```python
## 返回函数的函数
def make_adder(n):
	def adder(k):
		return k + n
	return adder
```
# Lecture 5 作用域
```python
def make_adder(n):
	def adder(k):
		return k + n
	return adder

## 将n = 3 输入父级函数
add_three = make_adder(3)
## k = 4 
add_three(4)
```
**嵌套def都有父作用域**
**当一个函数被定义时, 它的父级是当前作用域**
1. **当一个函数被调用时, 我们创建一个本地作用域**
2. **复制函数的父级到本地作用域**
3. **在本地作用域中将形参绑定到参数**
4. **在本地作用域中执行函数主体**

**lambda表达式**
**lambda (formal parameter): (expression)**
```
lambda x: x * x
```

**柯里化**

# Lecture 6 Sound
# Lecture 7 
**回溯**
# Lecture 8
```python
def delay(arg):
	print('delayed')
	def g():
		return arg
	return g

delay(delay)()(6)()
```

```python
def horse(mask):
	horse = mask
	def mask(horse):
		return horse
	return horse(mask) # return mask(2)
```

**装饰器**
```python
def my_decorator(func):
    def wrapper():
        print("函数开始执行")
        func()
        print("函数执行结束")

    return wrapper

@my_decorator
def hello():
    print("Hello")

# 等价于
def hello(): 
	print("Hello") 
	
	
hello = my_decorator(hello)
```
# Lecture 9 递归
```python
def print_all(x)
	print(x)
	return print_all
```

```python
def split(n):
	return n // 10, n % 10
	
def sum_digits(n):
	if n < 10:
		return n
	else:
		all_but_last, last = split(n)
		return sum_digits(all_but_last) + last
```
1. def 语句
2. 终止条件
3. 终止条件不进行递归
4. 其他条件进行递归
# Lecture 10 树递归
```python
def inverse_cascade(n):
	grow(n)
	print(n)
	shrink(n)

def f_then_g(f, g, n):
	if n:
		f(n)
		g(n)

grow = lambda n: f_then_g(grow, print, n // 10)
shrink = lambda n: f_then_g(print, shrink, n // 10)
```

```text
count(5, 3)
├── 使用3 → count(2, 3)
│   ├── 使用3 → count(-1, 3)
│   │   └── 0
│   │
│   └── 不使用3 → count(2, 2)
│       ├── 使用2 → count(0, 2)
│       │   └── 1
│       │
│       └── 不使用2 → count(2, 1)
│           ├── 使用1 → count(1, 1)
│           │   ├── 使用1 → count(0, 1)
│           │   │   └── 1
│           │   └── 不使用1 → count(1, 0)
│           │       └── 0
│           │
│           └── 不使用1 → count(2, 0)
│               └── 0
│
└── 不使用3 → count(5, 2)
    ├── 使用2 → count(3, 2)
    │   ├── 使用2 → count(1, 2)
    │   │   ├── 使用2 → count(-1, 2)
    │   │   │   └── 0
    │   │   └── 不使用2 → count(1, 1)
    │   │       ├── 使用1 → count(0, 1)
    │   │       │   └── 1
    │   │       └── 不使用1 → count(1, 0)
    │   │           └── 0
    │   │
    │   └── 不使用2 → count(3, 1)
    │       ├── 使用1 → count(2, 1)
    │       │   ├── 使用1 → count(1, 1)
    │       │   │   ├── 使用1 → count(0, 1)
    │       │   │   │   └── 1
    │       │   │   └── 不使用1 → count(1, 0)
    │       │   │       └── 0
    │       │   └── 不使用1 → count(2, 0)
    │       │       └── 0
    │       └── 不使用1 → count(3, 0)
    │           └── 0
    │
    └── 不使用2 → count(5, 1)
        ├── 使用1 → count(4, 1)
        │   ├── 使用1 → count(3, 1)
        │   │   └── ...
        │   └── 不使用1 → count(4, 0)
        │       └── 0
        └── 不使用1 → count(5, 0)
            └── 0
```
# Lecture 11 数组 队列
**递归>迭代**
```python
## 数组拼接
[2, 7] + digits * 2

list()

[x + 1 for x in odds if 25 % x == 0]
```
# Lecture 12 
# Lecture 13
# 作业
## hw
```python
def make_repeater(f, n):
	def repeater(x):
		if n == 0:
			return f(x)
		else:
			return f(make_repeater(f, n - 1)(x))
	return repeater
```
## lab
```python
# return直接返回字符串, 而print直接打印还能拼接
>>> def welcome():
...     print('Go')
...     return 'hello'
...
>>> def cal():
...     print('Bears')
...     return 'world'
...
>>> welcome()
Go
'hello'
>>> print(welcome(), cal())
Go
Bears
hello world
```
## proj