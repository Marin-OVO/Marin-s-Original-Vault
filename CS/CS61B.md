---
date:
tags:
  - 算法与数据结构
  - Java
---
# Lectures 1
Java非常注重面向对象编程, 所有的代码都应该放在一个类中
public class CLASSNAME
public static void main(String[] args)
## Java语法
1. 声明变量具体类型
2. 类型不能更改
3. 在运行前会检查所有变量类型是否正确(先编译后运行？)
4. 编译器+解释器

# HW01
# Lectures 2
有主方法才能调用运行
Class.Method![[Pasted image 20260915141432.png]]
Person     p     =     new Person();
    ↑        ↑                   ↑
类型      变量名         创建对象
1. 实例变量
2. 构造函数 => python: def __init__(self, ):
3. public void CLASSNAME -> 实例方法 非静态时必须引用参数 针对一个个体 特殊型 **对象是变量名**
   public static void CLASSNAME static方法不能访问实例变量 属于类 通用型整个类应该一致 适用于整个类 **对象是类名**
Dog smalldog; 声明变量类型
new Dog(5); 分配类内存 实例化？
small dog = new Dog(5); 添加引用 变量赋值

**Debugger**

# HW02
**打印字符串字符** str.charAt(i)
**添加字符** String str = ""; str += s.charAt(i)
# Lectures 3
