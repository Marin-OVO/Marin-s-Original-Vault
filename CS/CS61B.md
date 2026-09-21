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
# Lectures 3 数组
**分配变量**
```
Walrus someWalrus;
someWalrus = new Walrus(1000, 8.3);
```
new为Walrus(1000, 8.3)声明地址
someWalrus实际上是存的是Walrus(1000, 8.3)的地址
**数组**
```java
Planet p = new Planet(0, 0, 0, 0, 0, "blah.png");
int[] x = new int[]{0, 1, 2, 95, 4};

int[] a;
```

``` java
// java的数组是有固定长度, 如果想要无限数组只能这样
import java.util.List;
import java.util.LinkedList;
List<String> L = new LinkedList<>();
L.add("a");
```

## 1.链表
```java
package lec3_lists1;

public class Intlist{
	public int first;
	public IntList rest;
	
	public IntList(int f, IntList r){
		first = f;
		rest = r;
	}
	
	// 递归返回链表大小
	public int size(){
		if (rest == null){
			return 1;
		}
		return 1 + rest.size()
	}
	
	// 迭代返回链表大小
	public int iterativeSize(){
		int totalSize = 0;
		IntList p = this;
		while (p != null){
			totalSize += 1;
			p = p.rest;
		}
		return totalSize;
	}
	
	public int get(int i){
		if (i == 0){
			return first;
		}
		
		return rest.get(i - 1);
	}
	
	public static void main(String[] agrs){
		IntList L = new IntList;
		L
	}
}
```

# Lecture 4 数组
```java
// 
public class IntNode {
	public int item;
	public IntNode next;
	
	public IntNode(int i, IntNode n){
		item = i;
		next = n;
	}
}
```
```java
// 封装
public class SLList {
	// public IntNode head;
	// 私有化变量
	private IntNode head;
	
	private int size(IntNode p){
		if (p.next == null){
			return 1;
		}
		return 1 + size(p.next);
	}
	
	// 隐藏size方法
	public int size(){
		return size(head);
	}
	
	// 构造函数
	public SLList(int x){
		head = new IntNode(x, null);
	}
	
	public addFirst(int x){
		head = new IntNode(x, head);
	}
	
	public getFirst(){
		return head.item;
	}
}
```

```java
// 优化size()
public class SLList {
	private IntNode head;
	private int size;
	
	public int size(){
		return size;
	}
	
	// 构造函数
	public SLList(){
		head = null;
		size = 0;
	}
	
	public SLList(int x){
		head = new IntNode(x, null);
		size = 1;
	}
	
	public addFirst(int x){
		head = new IntNode(x, head);
		size += 1;
	}
	f
	public addLast(int x){
		IntNode p = head;
		
		while (p.next != null){
			p = p.next;
		}
		
		p.next = new IntNode(x, null);
		size += 1;
	}
	
	public getFirst(){
		return head.item;
	}
}
```

```java
// 虚拟节点: 防止空节点addLast报错
public class SLList {
	private IntNode sentinel;
	private int size;
	
	public int size(){
		return size;
	}
	
	// 构造函数
	public SLList(){
		sentinel = new IntNode(42, null);
		size = 0;
	}
	
	public SLList(int x){
		sentinel = new IntNode(42, null);
		sentinel.next = new IntNode(x, null);
		size = 1;
	}
	
	public addFirst(int x){
		sentinel.next = new IntNode(x, sentinel.next);
		size += 1;
	}
	f
	public addLast(int x){
		IntNode p = sentinel;
		
		while (p.next != null){
			p = p.next;
		}
		
		p.next = new IntNode(x, null);
		size += 1;
	}
	
	public getFirst(){
		return sentinel.next.item;
	}
}
```
