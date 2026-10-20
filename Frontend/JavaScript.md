# JavaScript 知识点整理

## 1. JavaScript 是什么

JavaScript 是一种用于网页交互和逻辑处理的编程语言。HTML 负责网页结构，CSS 负责网页样式，JavaScript 负责网页行为。

可以简单理解为：

| 技术 | 主要作用 |
| --- | --- |
| HTML | 定义网页有什么 |
| CSS | 决定网页长什么样 |
| JavaScript | 决定网页会做什么 |

JavaScript 可以实现：

- 按钮点击事件
- 表单验证
- 页面内容动态修改
- 动画效果
- 游戏逻辑
- 网络请求
- 数据处理
- 前端应用开发

---

## 2. 在 HTML 中引入 JavaScript

### 2.1 外部 JavaScript 文件

推荐将 JavaScript 单独写在 `.js` 文件中：

```html
<script src="app.js"></script>
```

常见写法：

```html
<head>
    <script src="app.js" defer></script>
</head>
```

`defer` 表示浏览器先解析 HTML，同时下载 JavaScript，等 HTML 解析完成后再执行 JavaScript。

也可以把 `<script>` 放在 `body` 最后：

```html
<body>
    <h1>Hello</h1>

    <script src="app.js"></script>
</body>
```

### 2.2 直接写 JavaScript

```html
<script>
    console.log("Hello JavaScript");
</script>
```

大型项目一般推荐使用外部 `.js` 文件。

---

## 3. 输出内容

### 3.1 控制台输出

```javascript
console.log("Hello");
```

常用于调试程序。

### 3.2 警告框

```javascript
alert("Hello");
```

### 3.3 浏览器控制台

按 `F12` 打开开发者工具，在 Console 中可以查看：

```javascript
console.log("测试");
```

输出结果：

```text
测试
```

---

## 4. 注释

单行注释：

```javascript
// 这是单行注释
```

多行注释：

```javascript
/*
这是
多行注释
*/
```

---

## 5. 变量

JavaScript 常用三种变量声明方式：

```javascript
let age = 20;
const name = "Tom";
var score = 100;
```

现代 JavaScript 中主要推荐使用：

```text
let   → 值之后可能变化
const → 值不准备重新赋值
```

通常不推荐新代码大量使用 `var`。

### 5.1 `let`

```javascript
let score = 0;
score = 10;
```

### 5.2 `const`

```javascript
const pi = 3.14159;
```

下面这样会报错：

```javascript
const pi = 3.14;
pi = 3.14159;
```

### 5.3 命名规则

变量名可以包含：

```text
字母
数字
_
$
```

但不能以数字开头。

正确：

```javascript
let userName;
let score1;
let _count;
let $value;
```

错误：

```javascript
let 1score;
```

常用命名方式是驼峰命名：

```javascript
let currentScore;
let highScore;
let userName;
```

---

## 6. 基本数据类型

JavaScript 常见基本类型：

| 类型 | 示例 |
| --- | --- |
| Number | `10`、`3.14` |
| String | `"Hello"` |
| Boolean | `true`、`false` |
| Undefined | `undefined` |
| Null | `null` |
| BigInt | `123n` |
| Symbol | `Symbol()` |

此外还有对象类型：

```text
Object
Array
Function
Date
Map
Set
```

---

## 7. Number 数字

```javascript
let a = 10;
let b = 3.14;
```

JavaScript 不区分整数和普通浮点数，通常都使用 `Number`。

常见运算：

```javascript
let a = 10 + 5;
let b = 10 - 5;
let c = 10 * 5;
let d = 10 / 5;
let e = 10 % 3;
let f = 2 ** 3;
```

结果：

```text
15
5
50
2
1
8
```

---

## 8. String 字符串

字符串可以使用：

```javascript
let a = "Hello";
let b = 'Hello';
let c = `Hello`;
```

### 8.1 字符串拼接

```javascript
let name = "Tom";
let message = "Hello " + name;
```

### 8.2 模板字符串

推荐使用反引号：

```javascript
let name = "Tom";
let age = 20;

let message = `My name is ${name}, I am ${age} years old.`;
```

模板字符串可以直接插入变量：

```javascript
`${变量}`
```

---

## 9. Boolean 布尔值

只有两个值：

```javascript
true
false
```

例如：

```javascript
let isRunning = true;
let isGameOver = false;
```

---

## 10. `null` 与 `undefined`

### 10.1 `undefined`

表示变量已经存在，但还没有赋值：

```javascript
let x;
console.log(x);
```

结果：

```text
undefined
```

### 10.2 `null`

表示程序员主动设置为空：

```javascript
let player = null;
```

可以简单理解：

```text
undefined → 还没有值
null      → 明确设置为空
```

---

## 11. `typeof`

可以查看数据类型：

```javascript
console.log(typeof 10);
console.log(typeof "Hello");
console.log(typeof true);
```

输出：

```text
number
string
boolean
```

例如：

```javascript
let score = 100;
console.log(typeof score);
```

---

## 12. 运算符

### 12.1 算术运算符

```javascript
+   加
-   减
*   乘
/   除
%   取余
**  幂
```

### 12.2 赋值运算符

```javascript
let x = 10;

x += 5;
x -= 2;
x *= 3;
x /= 2;
```

### 12.3 自增和自减

```javascript
x++;
x--;
```

### 12.4 比较运算符

```javascript
>
<
>=
<=
==
===
!=
!==
```

推荐优先使用：

```javascript
===
!==
```

例如：

```javascript
5 === 5
```

结果：

```text
true
```

而：

```javascript
5 === "5"
```

结果：

```text
false
```

### 12.5 `==` 与 `===`

```javascript
5 == "5"
```

结果：

```text
true
```

因为 `==` 会尝试进行类型转换。

```javascript
5 === "5"
```

结果：

```text
false
```

因为 `===` 同时比较值和类型。

现代 JavaScript 通常推荐使用 `===`。

---

## 13. 逻辑运算符

### 13.1 AND

```javascript
&&
```

例如：

```javascript
age >= 18 && hasTicket
```

### 13.2 OR

```javascript
||
```

例如：

```javascript
isAdmin || isOwner
```

### 13.3 NOT

```javascript
!
```

例如：

```javascript
!isRunning
```

---

## 14. 条件语句

### 14.1 `if`

```javascript
if (score >= 100) {
    console.log("成功");
}
```

### 14.2 `if...else`

```javascript
if (score >= 60) {
    console.log("及格");
} else {
    console.log("不及格");
}
```

### 14.3 `if...else if...else`

```javascript
if (score >= 90) {
    console.log("A");
} else if (score >= 80) {
    console.log("B");
} else if (score >= 60) {
    console.log("C");
} else {
    console.log("D");
}
```

---

## 15. 三元运算符

简单条件可以写成：

```javascript
let result = score >= 60 ? "及格" : "不及格";
```

结构：

```text
条件 ? 条件成立时的值 : 条件不成立时的值
```

---

## 16. `switch`

适合判断多个固定值：

```javascript
let direction = "left";

switch (direction) {
    case "left":
        console.log("向左");
        break;
    case "right":
        console.log("向右");
        break;
    default:
        console.log("未知方向");
}
```

---

## 17. 循环

### 17.1 `for`

```javascript
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

输出：

```text
0
1
2
3
4
```

### 17.2 `while`

```javascript
let i = 0;

while (i < 5) {
    console.log(i);
    i++;
}
```

### 17.3 `for...of`

常用于遍历数组：

```javascript
const numbers = [10, 20, 30];

for (const number of numbers) {
    console.log(number);
}
```

### 17.4 `for...in`

主要用于遍历对象属性：

```javascript
const user = {
    name: "Tom",
    age: 20
};

for (const key in user) {
    console.log(key, user[key]);
}
```

---

## 18. `break` 与 `continue`

### 18.1 `break`

立即结束循环：

```javascript
for (let i = 0; i < 10; i++) {
    if (i === 5) {
        break;
    }

    console.log(i);
}
```

### 18.2 `continue`

跳过当前这一次循环：

```javascript
for (let i = 0; i < 5; i++) {
    if (i === 2) {
        continue;
    }

    console.log(i);
}
```

---

## 19. 函数

函数用于封装可重复执行的代码。

### 19.1 普通函数

```javascript
function add(a, b) {
    return a + b;
}
```

调用：

```javascript
let result = add(2, 3);
```

### 19.2 参数

```javascript
function greet(name) {
    console.log(`Hello ${name}`);
}

greet("Tom");
```

### 19.3 返回值

```javascript
function square(x) {
    return x * x;
}
```

### 19.4 没有 `return`

如果函数没有显式返回值：

```javascript
function test() {
    console.log("Hello");
}
```

函数默认返回：

```text
undefined
```

---

## 20. 函数表达式

函数也可以保存到变量中：

```javascript
const add = function (a, b) {
    return a + b;
};
```

---

## 21. 箭头函数

现代 JavaScript 常见：

```javascript
const add = (a, b) => {
    return a + b;
};
```

如果只有一个表达式，可以简写：

```javascript
const add = (a, b) => a + b;
```

单个参数可以写成：

```javascript
const square = x => x * x;
```

---

## 22. 作用域

变量并不是任何地方都可以访问。

### 22.1 全局作用域

```javascript
let score = 0;

function test() {
    console.log(score);
}
```

### 22.2 函数作用域

```javascript
function test() {
    let x = 10;
}

console.log(x);
```

这里访问不到 `x`。

### 22.3 块级作用域

`let` 和 `const` 具有块级作用域：

```javascript
if (true) {
    let x = 10;
}

console.log(x);
```

这里也访问不到 `x`。

---

## 23. 数组

数组用于保存多个值：

```javascript
const numbers = [10, 20, 30];
```

索引从 `0` 开始：

```javascript
console.log(numbers[0]);
console.log(numbers[1]);
```

输出：

```text
10
20
```

### 23.1 修改数组

```javascript
numbers[0] = 100;
```

### 23.2 数组长度

```javascript
numbers.length
```

### 23.3 添加元素

末尾添加：

```javascript
numbers.push(40);
```

开头添加：

```javascript
numbers.unshift(0);
```

### 23.4 删除元素

删除末尾：

```javascript
numbers.pop();
```

删除开头：

```javascript
numbers.shift();
```

---

## 24. 常用数组方法

### 24.1 `forEach`

```javascript
const numbers = [1, 2, 3];

numbers.forEach(number => {
    console.log(number);
});
```

### 24.2 `map`

把数组每个元素处理后生成新数组：

```javascript
const numbers = [1, 2, 3];

const doubled = numbers.map(x => x * 2);
```

结果：

```javascript
[2, 4, 6]
```

### 24.3 `filter`

筛选元素：

```javascript
const numbers = [1, 2, 3, 4];

const result = numbers.filter(x => x > 2);
```

结果：

```javascript
[3, 4]
```

### 24.4 `find`

找到第一个满足条件的元素：

```javascript
const numbers = [1, 2, 3, 4];

const result = numbers.find(x => x > 2);
```

结果：

```text
3
```

### 24.5 `includes`

```javascript
const numbers = [1, 2, 3];

console.log(numbers.includes(2));
```

结果：

```text
true
```

---

## 25. 对象

对象用于保存一组有关联的数据：

```javascript
const user = {
    name: "Tom",
    age: 20,
    isAdmin: false
};
```

访问属性：

```javascript
console.log(user.name);
console.log(user.age);
```

也可以写：

```javascript
console.log(user["name"]);
```

修改属性：

```javascript
user.age = 21;
```

增加属性：

```javascript
user.city = "Shanghai";
```

---

## 26. 对象中的函数

对象可以包含函数：

```javascript
const player = {
    name: "Tom",
    score: 0,

    move() {
        console.log("Player moved");
    }
};
```

调用：

```javascript
player.move();
```

---

## 27. 解构赋值

数组解构：

```javascript
const numbers = [10, 20];

const [a, b] = numbers;
```

对象解构：

```javascript
const user = {
    name: "Tom",
    age: 20
};

const { name, age } = user;
```

---

## 28. 展开运算符 `...`

数组展开：

```javascript
const a = [1, 2];
const b = [...a, 3, 4];
```

结果：

```javascript
[1, 2, 3, 4]
```

对象展开：

```javascript
const user = {
    name: "Tom"
};

const newUser = {
    ...user,
    age: 20
};
```

---

## 29. DOM 是什么

DOM（Document Object Model）是浏览器把 HTML 页面转换成的一棵对象树。

例如 HTML：

```html
<body>
    <h1 id="title">Hello</h1>
    <button id="btn">点击我</button>
</body>
```

JavaScript 可以通过 DOM 找到并修改这些元素。

---

## 30. 获取 HTML 元素

### 30.1 `getElementById`

HTML：

```html
<h1 id="title">Hello</h1>
```

JavaScript：

```javascript
const title = document.getElementById("title");
```

### 30.2 `querySelector`

```javascript
const title = document.querySelector("#title");
```

选择 class：

```javascript
const card = document.querySelector(".card");
```

选择标签：

```javascript
const button = document.querySelector("button");
```

### 30.3 `querySelectorAll`

选择多个元素：

```javascript
const buttons = document.querySelectorAll("button");
```

---

## 31. 修改 HTML 内容

HTML：

```html
<h1 id="title">Hello</h1>
```

JavaScript：

```javascript
const title = document.getElementById("title");

title.textContent = "Snake Game";
```

也可以：

```javascript
title.innerHTML = "<span>Snake Game</span>";
```

一般纯文字优先使用：

```javascript
textContent
```

---

## 32. 修改 CSS

HTML：

```html
<h1 id="title">Hello</h1>
```

JavaScript：

```javascript
const title = document.getElementById("title");

title.style.color = "red";
title.style.fontSize = "40px";
```

更推荐通过 class 控制样式：

```javascript
title.classList.add("active");
title.classList.remove("active");
title.classList.toggle("active");
```

---

## 33. 事件

事件表示用户或浏览器发生了某种操作，例如：

```text
点击
键盘输入
鼠标移动
页面加载
表单提交
```

### 33.1 点击事件

HTML：

```html
<button id="btn">点击我</button>
```

JavaScript：

```javascript
const btn = document.getElementById("btn");

btn.addEventListener("click", function () {
    console.log("按钮被点击");
});
```

也可以使用箭头函数：

```javascript
btn.addEventListener("click", () => {
    console.log("按钮被点击");
});
```

---

## 34. 常见事件

| 事件 | 含义 |
| --- | --- |
| `click` | 鼠标点击 |
| `dblclick` | 双击 |
| `keydown` | 键盘按下 |
| `keyup` | 键盘松开 |
| `input` | 输入内容发生变化 |
| `change` | 表单值变化 |
| `submit` | 表单提交 |
| `mousemove` | 鼠标移动 |
| `mouseenter` | 鼠标进入 |
| `mouseleave` | 鼠标离开 |
| `load` | 页面或资源加载完成 |

---

## 35. 键盘事件

Snake Game 中非常常用：

```javascript
document.addEventListener("keydown", event => {
    console.log(event.key);
});
```

例如：

```javascript
document.addEventListener("keydown", event => {
    if (event.key === "ArrowUp") {
        console.log("向上");
    }

    if (event.key === "ArrowDown") {
        console.log("向下");
    }
});
```

常见方向键：

```text
ArrowUp
ArrowDown
ArrowLeft
ArrowRight
```

---

## 36. 事件对象 `event`

事件处理函数通常会收到一个事件对象：

```javascript
button.addEventListener("click", event => {
    console.log(event);
});
```

键盘事件：

```javascript
document.addEventListener("keydown", event => {
    console.log(event.key);
});
```

鼠标事件：

```javascript
document.addEventListener("mousemove", event => {
    console.log(event.clientX, event.clientY);
});
```

---

## 37. 表单事件

HTML：

```html
<form id="form">
    <input id="name" type="text">
    <button type="submit">提交</button>
</form>
```

JavaScript：

```javascript
const form = document.getElementById("form");

form.addEventListener("submit", event => {
    event.preventDefault();
    console.log("表单提交");
});
```

`event.preventDefault()` 用于阻止浏览器默认行为。

---

## 38. 定时器

### 38.1 `setTimeout`

延迟执行一次：

```javascript
setTimeout(() => {
    console.log("Hello");
}, 1000);
```

`1000` 表示 1000 毫秒，也就是 1 秒。

### 38.2 `setInterval`

重复执行：

```javascript
const timer = setInterval(() => {
    console.log("运行");
}, 1000);
```

停止：

```javascript
clearInterval(timer);
```

Snake Game 经常用定时器控制蛇移动。

---

## 39. `Math`

### 39.1 随机数

```javascript
Math.random()
```

得到：

```text
0 <= x < 1
```

生成 `0` 到 `9` 的随机整数：

```javascript
Math.floor(Math.random() * 10);
```

### 39.2 常见方法

```javascript
Math.floor(3.8);
Math.ceil(3.2);
Math.round(3.5);
Math.max(1, 5, 3);
Math.min(1, 5, 3);
Math.abs(-10);
Math.sqrt(16);
```

---

## 40. JSON

JSON 常用于前后端传输数据。

对象：

```javascript
const user = {
    name: "Tom",
    age: 20
};
```

转换成 JSON：

```javascript
const json = JSON.stringify(user);
```

JSON 转回对象：

```javascript
const obj = JSON.parse(json);
```

---

## 41. `localStorage`

浏览器可以在本地保存少量数据。

保存：

```javascript
localStorage.setItem("highScore", "100");
```

读取：

```javascript
const highScore = localStorage.getItem("highScore");
```

删除：

```javascript
localStorage.removeItem("highScore");
```

Snake Game 可以用它保存最高分：

```javascript
localStorage.setItem("highScore", highScore);
```

---

## 42. Canvas 基础

HTML：

```html
<canvas id="myCanvas" width="400" height="300"></canvas>
```

JavaScript：

```javascript
const canvas = document.getElementById("myCanvas");
const ctx = canvas.getContext("2d");
```

其中：

```text
canvas → HTML 画布元素
ctx    → 2D 绘图上下文
```

### 42.1 绘制矩形

```javascript
ctx.fillRect(50, 50, 100, 100);
```

参数：

```text
x
y
width
height
```

即：

```javascript
ctx.fillRect(x, y, width, height);
```

### 42.2 清空画布

```javascript
ctx.clearRect(0, 0, canvas.width, canvas.height);
```

### 42.3 设置颜色

```javascript
ctx.fillStyle = "green";
ctx.fillRect(50, 50, 20, 20);
```

---

## 43. Snake Game 中 Canvas 的基本思路

蛇可以表示成数组：

```javascript
const snake = [
    { x: 100, y: 100 },
    { x: 80, y: 100 },
    { x: 60, y: 100 }
];
```

绘制：

```javascript
snake.forEach(part => {
    ctx.fillRect(part.x, part.y, 20, 20);
});
```

食物：

```javascript
const food = {
    x: 200,
    y: 100
};
```

绘制：

```javascript
ctx.fillRect(food.x, food.y, 20, 20);
```

---

## 44. 异步 JavaScript

有些操作不会立即完成，例如：

```text
网络请求
读取文件
定时器
数据库请求
```

JavaScript 使用异步机制处理这些任务。

---

## 45. Promise

Promise 表示一个未来可能完成的结果。

```javascript
const promise = new Promise((resolve, reject) => {
    resolve("成功");
});
```

使用：

```javascript
promise.then(result => {
    console.log(result);
});
```

---

## 46. `async` 和 `await`

现代 JavaScript 常用：

```javascript
async function loadData() {
    const response = await fetch("https://example.com/data");
    const data = await response.json();

    console.log(data);
}
```

`await` 表示等待异步操作完成。

---

## 47. `fetch`

用于发送网络请求：

```javascript
fetch("https://example.com/data")
    .then(response => response.json())
    .then(data => {
        console.log(data);
    });
```

也可以：

```javascript
async function loadData() {
    const response = await fetch("https://example.com/data");
    const data = await response.json();

    console.log(data);
}
```

---

## 48. 错误处理

### 48.1 `try...catch`

```javascript
try {
    const result = riskyOperation();
    console.log(result);
} catch (error) {
    console.error(error);
}
```

### 48.2 手动抛出错误

```javascript
throw new Error("发生错误");
```

---

## 49. 模块化

JavaScript 可以把代码拆成多个文件。

### `math.js`

```javascript
export function add(a, b) {
    return a + b;
}
```

### `app.js`

```javascript
import { add } from "./math.js";

console.log(add(2, 3));
```

HTML：

```html
<script type="module" src="app.js"></script>
```

---

## 50. 类 `class`

JavaScript 支持面向对象写法：

```javascript
class Player {
    constructor(name, score) {
        this.name = name;
        this.score = score;
    }

    move() {
        console.log(`${this.name} moved`);
    }
}
```

创建对象：

```javascript
const player = new Player("Tom", 0);
```

调用：

```javascript
player.move();
```

---

## 51. `this`

`this` 通常表示当前对象：

```javascript
const player = {
    name: "Tom",

    sayHello() {
        console.log(this.name);
    }
};
```

调用：

```javascript
player.sayHello();
```

输出：

```text
Tom
```

---

## 52. 常见 DOM 项目结构

目录：

```text
project/
├── index.html
├── css/
│   └── style.css
└── js/
    └── app.js
```

HTML：

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>JavaScript Demo</title>
    <link rel="stylesheet" href="css/style.css">
    <script src="js/app.js" defer></script>
</head>

<body>
    <button id="btn">点击我</button>
</body>
</html>
```

JavaScript：

```javascript
const btn = document.getElementById("btn");

btn.addEventListener("click", () => {
    alert("Hello");
});
```

---

## 53. Snake Game 推荐结构

HTML：

```html
<canvas id="myCanvas" width="400" height="300"></canvas>

<div class="score">
    <span>当前分数：<span id="score">0</span></span>
    <span>最高分数：<span id="highScore">0</span></span>
</div>

<button id="startBtn">开始游戏</button>
<button id="pauseBtn">暂停游戏</button>
<button id="restartBtn">重新开始</button>
```

JavaScript 初始化：

```javascript
const canvas = document.getElementById("myCanvas");
const ctx = canvas.getContext("2d");

const scoreElement = document.getElementById("score");
const highScoreElement = document.getElementById("highScore");

const startBtn = document.getElementById("startBtn");
const pauseBtn = document.getElementById("pauseBtn");
const restartBtn = document.getElementById("restartBtn");
```

游戏常见变量：

```javascript
let score = 0;
let direction = "right";
let gameTimer = null;
let isRunning = false;
```

游戏常见函数：

```text
startGame()
pauseGame()
restartGame()
updateGame()
drawGame()
moveSnake()
generateFood()
checkCollision()
```

---

## 54. 常见错误

### 54.1 找不到 HTML 元素

错误：

```javascript
const btn = document.getElementById("button");
```

但 HTML 是：

```html
<button id="btn">按钮</button>
```

`id` 必须完全一致。

### 54.2 使用了不存在的变量

```javascript
console.log(score);
```

如果 `score` 没有声明，会报错。

### 54.3 `=` 与 `===` 混淆

错误：

```javascript
if (score = 10) {
}
```

这是赋值。

正确：

```javascript
if (score === 10) {
}
```

这是比较。

### 54.4 忘记调用函数

```javascript
startGame;
```

只是引用函数。

真正执行：

```javascript
startGame();
```

### 54.5 无限循环

```javascript
while (true) {
}
```

如果没有退出条件，页面可能卡死。

---

## 55. JavaScript 编写习惯

建议：

1. 优先使用 `const`，需要重新赋值时再使用 `let`。
2. 优先使用 `===` 和 `!==`。
3. 使用清晰的变量名，例如 `currentScore`，不要大量使用 `a`、`b`、`x`。
4. 一个函数尽量只负责一件事情。
5. 相似逻辑封装成函数。
6. 避免重复代码。
7. DOM 元素获取尽量集中在文件前面。
8. 常量和配置集中管理。
9. 用 `console.log()` 调试，但完成后删除无用调试输出。
10. 保持缩进统一。

---

## 56. 初学阶段重点掌握

推荐学习顺序：

```text
变量 let / const
↓
Number / String / Boolean
↓
运算符
↓
if / else
↓
for / while
↓
函数
↓
数组
↓
对象
↓
DOM
↓
事件
↓
定时器
↓
Canvas
↓
异步 JavaScript
↓
模块化
```

如果目标是做 Snake Game，最需要优先掌握：

```text
变量
数组
对象
函数
if
循环
DOM
键盘事件
setInterval
Canvas
```

---

## 57. JavaScript 常用语法速查

### 变量

```javascript
let score = 0;
const size = 20;
```

### 条件

```javascript
if (score > 10) {
    console.log("大于 10");
}
```

### 循环

```javascript
for (let i = 0; i < 10; i++) {
    console.log(i);
}
```

### 函数

```javascript
function add(a, b) {
    return a + b;
}
```

### 箭头函数

```javascript
const add = (a, b) => a + b;
```

### 数组

```javascript
const numbers = [1, 2, 3];
numbers.push(4);
```

### 对象

```javascript
const player = {
    x: 100,
    y: 100
};
```

### 获取 DOM

```javascript
const btn = document.getElementById("btn");
```

### 点击事件

```javascript
btn.addEventListener("click", () => {
    console.log("clicked");
});
```

### 键盘事件

```javascript
document.addEventListener("keydown", event => {
    console.log(event.key);
});
```

### 定时器

```javascript
const timer = setInterval(() => {
    console.log("running");
}, 1000);
```

### Canvas

```javascript
const canvas = document.getElementById("myCanvas");
const ctx = canvas.getContext("2d");

ctx.fillRect(0, 0, 20, 20);
```

---

## 58. 核心理解

JavaScript 初学阶段最重要的不是记住所有语法，而是理解程序的基本运行逻辑：

```text
保存数据
↓
判断条件
↓
重复执行
↓
封装函数
↓
监听用户操作
↓
修改页面或数据
```

例如 Snake Game 的完整逻辑本质上就是：

```text
创建蛇和食物
↓
监听键盘方向
↓
定时移动蛇
↓
重新绘制 Canvas
↓
判断是否吃到食物
↓
更新分数
↓
判断是否碰撞
↓
游戏结束或继续
```

掌握这些核心逻辑后，再学习更复杂的 JavaScript 框架会容易很多。
