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
