# CSS 知识点整理

## 1. CSS 是什么

CSS（Cascading Style Sheets，层叠样式表）用于控制网页的外观和布局，例如颜色、字体、间距、边框、位置、动画和响应式效果。

HTML 和 CSS 的关系可以简单理解为：

```text
HTML → 决定网页有什么
CSS  → 决定网页长什么样
```

例如 HTML：

```html
<h1>Hello</h1>
```

CSS：

```css
h1 {
    color: red;
    font-size: 40px;
}
```

这样浏览器中的 `Hello` 就会显示为红色，并且字号为 40px。

---

## 2. CSS 的基本语法

CSS 的基本结构：

```css
选择器 {
    属性: 属性值;
}
```

例如：

```css
p {
    color: blue;
    font-size: 18px;
}
```

其中：

```text
p              → 选择器
color          → 属性
blue           → 属性值
font-size      → 属性
18px           → 属性值
```

每条 CSS 声明通常以分号 `;` 结束。

---

## 3. CSS 的三种使用方式

### 3.1 外部样式表

推荐方式，将 CSS 单独写在 `.css` 文件中。

HTML：

```html
<link rel="stylesheet" href="style.css">
```

CSS：

```css
h1 {
    color: red;
}
```

优点：

- HTML 和 CSS 分离
- 代码更整洁
- 多个页面可以共用同一个 CSS 文件
- 更适合实际项目

### 3.2 内部样式

直接写在 HTML 的 `<style>` 标签里：

```html
<style>
    h1 {
        color: red;
    }
</style>
```

### 3.3 行内样式

直接写在元素的 `style` 属性中：

```html
<h1 style="color: red;">Hello</h1>
```

一般不建议大量使用行内样式。

---

## 4. 常用选择器

### 4.1 标签选择器

选择所有指定标签：

```css
p {
    color: black;
}
```

表示所有 `<p>` 元素都应用该样式。

### 4.2 class 选择器

HTML：

```html
<p class="warning">警告</p>
```

CSS：

```css
.warning {
    color: red;
}
```

class 选择器以 `.` 开头。

### 4.3 id 选择器

HTML：

```html
<h1 id="title">标题</h1>
```

CSS：

```css
#title {
    color: blue;
}
```

id 选择器以 `#` 开头。

### 4.4 通配符选择器

```css
* {
    margin: 0;
    padding: 0;
}
```

`*` 表示选择所有元素。

### 4.5 群组选择器

```css
h1,
h2,
h3 {
    color: black;
}
```

多个选择器之间使用逗号分隔。

---

## 5. 后代、子元素和兄弟选择器

### 5.1 后代选择器

```css
header a {
    color: white;
}
```

表示选择 `header` 内部所有的 `a` 元素。

### 5.2 直接子元素选择器

```css
header > nav {
    margin-top: 10px;
}
```

只选择 `header` 的直接子元素 `nav`。

### 5.3 相邻兄弟选择器

```css
h1 + p {
    color: gray;
}
```

选择紧跟在 `h1` 后面的第一个 `p`。

### 5.4 通用兄弟选择器

```css
h1 ~ p {
    color: gray;
}
```

选择 `h1` 后面的所有同级 `p`。

---

## 6. 属性选择器

可以按照 HTML 属性选择元素。

```css
input[type="text"] {
    border: 1px solid gray;
}
```

例如：

```html
<input type="text">
<input type="password">
```

只有 `type="text"` 的输入框会被选中。

---

## 7. 伪类

伪类用于描述元素的某种状态。

### 7.1 `:hover`

鼠标悬停：

```css
button:hover {
    background-color: black;
    color: white;
}
```

### 7.2 `:focus`

元素获得焦点：

```css
input:focus {
    border-color: blue;
}
```

### 7.3 `:active`

元素正在被点击：

```css
button:active {
    transform: scale(0.98);
}
```

### 7.4 `:first-child`

选择第一个子元素：

```css
li:first-child {
    color: red;
}
```

### 7.5 `:last-child`

```css
li:last-child {
    color: blue;
}
```

### 7.6 `:nth-child()`

```css
li:nth-child(2) {
    color: green;
}
```

选择第二个子元素。

---

## 8. 伪元素

伪元素用于选择元素的一部分，或创建额外内容。

### 8.1 `::before`

```css
.title::before {
    content: "★ ";
}
```

### 8.2 `::after`

```css
.title::after {
    content: " ★";
}
```

### 8.3 `::first-letter`

```css
p::first-letter {
    font-size: 30px;
}
```

---

## 9. 颜色

### 9.1 颜色名称

```css
color: red;
```

### 9.2 十六进制

```css
color: #ff0000;
```

### 9.3 RGB

```css
color: rgb(255, 0, 0);
```

### 9.4 RGBA

```css
background-color: rgba(0, 0, 0, 0.5);
```

最后一个值表示透明度，范围通常为 `0 ~ 1`。

---

## 10. 字体与文本

### 10.1 字体大小

```css
font-size: 20px;
```

### 10.2 字体粗细

```css
font-weight: bold;
```

也可以：

```css
font-weight: 400;
font-weight: 700;
```

### 10.3 字体类型

```css
font-family: Arial, sans-serif;
```

### 10.4 文本对齐

```css
text-align: center;
```

常见值：

```text
left
center
right
justify
```

### 10.5 行高

```css
line-height: 1.6;
```

### 10.6 字符间距

```css
letter-spacing: 2px;
```

### 10.7 文本装饰

```css
text-decoration: none;
```

常用于去掉链接下划线：

```css
a {
    text-decoration: none;
}
```

### 10.8 文本转换

```css
text-transform: uppercase;
```

常见值：

```text
uppercase
lowercase
capitalize
```

---

## 11. 长度单位

### 11.1 `px`

像素：

```css
width: 200px;
```

适合固定尺寸。

### 11.2 `%`

相对于父元素：

```css
width: 80%;
```

### 11.3 `vw`

相对于视口宽度：

```css
width: 50vw;
```

`100vw` 表示整个浏览器可视区域宽度。

### 11.4 `vh`

相对于视口高度：

```css
height: 100vh;
```

### 11.5 `em`

相对于当前元素字体大小：

```css
padding: 1em;
```

### 11.6 `rem`

相对于根元素 `html` 的字体大小：

```css
font-size: 1.5rem;
```

---

## 12. CSS 盒模型

HTML 元素可以理解为一个盒子。

盒模型由四层组成：

```text
margin
└── border
    └── padding
        └── content
```

对应：

```css
.box {
    width: 200px;
    padding: 20px;
    border: 2px solid black;
    margin: 30px;
}
```

### 12.1 content

元素实际内容区域。

### 12.2 padding

内容和边框之间的距离。

```css
padding: 20px;
```

### 12.3 border

边框。

```css
border: 1px solid black;
```

### 12.4 margin

元素与其他元素之间的距离。

```css
margin: 20px;
```

---

## 13. `box-sizing`

默认情况下：

```css
width: 200px;
padding: 20px;
border: 2px solid black;
```

最终实际宽度会超过 200px。

通常项目中会写：

```css
* {
    box-sizing: border-box;
}
```

这样设置后：

```css
width: 200px;
```

表示元素最终总宽度就是 200px，其中包含 padding 和 border。

这是非常常见的 CSS 初始化写法。

---

## 14. margin 和 padding 的写法

四个方向：

```css
margin-top: 10px;
margin-right: 20px;
margin-bottom: 30px;
margin-left: 40px;
```

简写：

```css
margin: 10px;
```

表示四个方向都是 10px。

```css
margin: 10px 20px;
```

表示：

```text
上下 10px
左右 20px
```

```css
margin: 10px 20px 30px 40px;
```

顺序：

```text
上 → 右 → 下 → 左
```

可以记成顺时针方向。

padding 同理。

---

## 15. 边框

基本写法：

```css
border: 1px solid black;
```

分别表示：

```text
1px    → 边框宽度
solid  → 边框样式
black  → 边框颜色
```

常见样式：

```text
solid
dashed
dotted
double
```

单独设置：

```css
border-width: 2px;
border-style: solid;
border-color: red;
```

---

## 16. 圆角

```css
border-radius: 10px;
```

做圆形：

```css
.avatar {
    width: 100px;
    height: 100px;
    border-radius: 50%;
}
```

---

## 17. 背景

### 17.1 背景颜色

```css
background-color: #f5f5f5;
```

### 17.2 背景图片

```css
background-image: url("images/bg.jpg");
```

### 17.3 是否重复

```css
background-repeat: no-repeat;
```

### 17.4 背景尺寸

```css
background-size: cover;
```

常见：

```text
cover   → 尽量铺满
contain → 完整显示图片
```

### 17.5 背景位置

```css
background-position: center;
```

---

## 18. 宽度和高度

```css
width: 300px;
height: 200px;
```

最小尺寸：

```css
min-width: 200px;
min-height: 100px;
```

最大尺寸：

```css
max-width: 1200px;
max-height: 600px;
```

常见页面容器：

```css
.container {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
}
```

其中：

```css
margin: 0 auto;
```

常用于让固定宽度或最大宽度的块级元素水平居中。

---

## 19. `display`

`display` 控制元素如何显示。

### 19.1 `block`

块级元素：

```css
display: block;
```

通常独占一行，可以设置宽高。

### 19.2 `inline`

行内元素：

```css
display: inline;
```

通常不会独占一行，宽高控制受限。

### 19.3 `inline-block`

```css
display: inline-block;
```

既可以和其他元素在同一行，又可以设置宽高。

### 19.4 `none`

```css
display: none;
```

元素完全不显示，也不占位置。

### 19.5 `flex`

```css
display: flex;
```

启用 Flex 布局。

### 19.6 `grid`

```css
display: grid;
```

启用 Grid 布局。

---

## 20. Flex 布局

Flex 是非常常用的一维布局方式。

基本写法：

```css
.container {
    display: flex;
}
```

子元素默认从左向右排列。

### 20.1 主轴方向

```css
flex-direction: row;
```

常见值：

```text
row
row-reverse
column
column-reverse
```

### 20.2 主轴对齐

```css
justify-content: center;
```

常见值：

```text
flex-start
center
flex-end
space-between
space-around
space-evenly
```

### 20.3 交叉轴对齐

```css
align-items: center;
```

常见值：

```text
stretch
flex-start
center
flex-end
```

### 20.4 换行

```css
flex-wrap: wrap;
```

### 20.5 元素间距

```css
gap: 20px;
```

### 20.6 常见水平垂直居中

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

### 20.7 `flex`

```css
.item {
    flex: 1;
}
```

表示元素可以自动分配剩余空间。

---

## 21. Grid 布局

Grid 更适合二维网格布局。

基本写法：

```css
.container {
    display: grid;
}
```

### 21.1 设置列

```css
grid-template-columns: 1fr 1fr 1fr;
```

表示三列平均分配。

也可以写：

```css
grid-template-columns: repeat(3, 1fr);
```

### 21.2 设置间距

```css
gap: 20px;
```

### 21.3 自适应布局

```css
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
```

适合卡片列表等响应式布局。

---

## 22. position 定位

### 22.1 `static`

默认定位：

```css
position: static;
```

### 22.2 `relative`

相对定位：

```css
position: relative;
top: 10px;
left: 20px;
```

元素仍然保留原来的位置空间。

### 22.3 `absolute`

绝对定位：

```css
position: absolute;
top: 0;
right: 0;
```

元素脱离正常文档流。

如果父元素设置：

```css
position: relative;
```

那么绝对定位元素通常相对于该父元素定位。

### 22.4 `fixed`

固定定位：

```css
position: fixed;
bottom: 20px;
right: 20px;
```

元素相对于浏览器窗口固定。

### 22.5 `sticky`

粘性定位：

```css
position: sticky;
top: 0;
```

常用于吸顶导航栏。

---

## 23. `z-index`

控制元素覆盖顺序：

```css
.modal {
    position: fixed;
    z-index: 1000;
}
```

通常只有定位元素或特定布局上下文中的元素才会受到 `z-index` 影响。

数值越大，一般越靠上显示。

---

## 24. overflow

控制内容超出容器时如何处理。

```css
overflow: hidden;
```

常见值：

```text
visible
hidden
scroll
auto
```

例如：

```css
.box {
    width: 200px;
    height: 100px;
    overflow: auto;
}
```

内容超出时自动出现滚动条。

---

## 25. 阴影

### 25.1 盒子阴影

```css
box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
```

基本形式：

```text
水平偏移 垂直偏移 模糊程度 颜色
```

### 25.2 文字阴影

```css
text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.3);
```

---

## 26. `opacity`

控制透明度：

```css
opacity: 0.5;
```

范围：

```text
0   → 完全透明
1   → 完全不透明
```

---

## 27. `cursor`

控制鼠标样式：

```css
button {
    cursor: pointer;
}
```

按钮上常用 `pointer`，表示鼠标变成手型。

---

## 28. transition 过渡动画

让属性变化更加平滑：

```css
button {
    background-color: black;
    transition: background-color 0.3s;
}

button:hover {
    background-color: gray;
}
```

也可以：

```css
transition: all 0.3s ease;
```

常见时间函数：

```text
linear
ease
ease-in
ease-out
ease-in-out
```

---

## 29. transform 变换

### 29.1 移动

```css
transform: translateX(20px);
```

### 29.2 缩放

```css
transform: scale(1.1);
```

### 29.3 旋转

```css
transform: rotate(45deg);
```

### 29.4 综合使用

```css
button:hover {
    transform: translateY(-2px) scale(1.05);
}
```

---

## 30. animation 动画

定义动画：

```css
@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(200px);
    }
}
```

应用动画：

```css
.box {
    animation: move 2s ease infinite;
}
```

常见参数：

```text
move      → 动画名称
2s        → 持续时间
ease      → 动画速度变化
infinite  → 无限循环
```

---

## 31. CSS 变量

可以定义重复使用的值：

```css
:root {
    --main-color: #3498db;
    --spacing: 16px;
}
```

使用：

```css
button {
    background-color: var(--main-color);
    padding: var(--spacing);
}
```

适合统一管理主题颜色、间距等。

---

## 32. CSS 优先级

当多个 CSS 规则作用于同一个元素时，需要判断谁优先。

大致优先级：

```text
!important
↓
行内样式
↓
id 选择器
↓
class / 属性 / 伪类选择器
↓
标签 / 伪元素选择器
```

例如：

```css
p {
    color: black;
}

.text {
    color: blue;
}

#intro {
    color: red;
}
```

HTML：

```html
<p id="intro" class="text">Hello</p>
```

最终通常显示红色，因为 `#intro` 优先级更高。

不建议频繁使用：

```css
!important
```

因为会让样式难以维护。

---

## 33. CSS 层叠

CSS 中后定义的规则可能覆盖前面的规则。

例如：

```css
p {
    color: red;
}

p {
    color: blue;
}
```

最终通常是：

```text
blue
```

前提是两个规则的优先级相同。

---

## 34. 继承

某些 CSS 属性会从父元素继承给子元素。

例如：

```css
body {
    color: black;
    font-family: Arial;
}
```

内部很多文字元素会自动继承这些设置。

常见容易继承的属性：

```text
color
font-family
font-size
line-height
```

很多布局属性不会自动继承，例如：

```text
margin
padding
border
width
height
```

---

## 35. 响应式设计

响应式设计用于让网页适应不同屏幕尺寸。

### 35.1 媒体查询

```css
@media (max-width: 768px) {
    .container {
        width: 100%;
    }
}
```

表示当屏幕宽度不超过 768px 时应用该样式。

### 35.2 常见思路

```text
桌面端
↓
平板
↓
手机
```

响应式布局通常配合：

```text
%
rem
vw
vh
flex
grid
max-width
media query
```

---

## 36. 图片自适应

常见写法：

```css
img {
    max-width: 100%;
    height: auto;
}
```

这样图片不会超过父元素宽度，并保持原始宽高比例。

---

## 37. 常见 CSS 初始化

一个常见的基础初始化：

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
}

img {
    max-width: 100%;
    display: block;
}

a {
    color: inherit;
    text-decoration: none;
}

button,
input {
    font: inherit;
}
```

作用是减少浏览器默认样式带来的差异。

---

## 38. CSS 命名建议

class 名称应尽量有意义。

推荐：

```css
.game-container
.score-board
.start-button
.main-header
```

不推荐：

```css
.a
.box1
.test
.abc
```

推荐使用小写字母和短横线：

```text
snake-game
score-board
control-panel
```

---

## 39. 一个简单页面的 CSS 示例

HTML：

```html
<body>
    <header>
        <h1>Snake Game</h1>
    </header>

    <main class="game-container">
        <canvas id="myCanvas" width="400" height="300"></canvas>

        <section class="controls">
            <button>开始游戏</button>
            <button>暂停游戏</button>
            <button>重新开始</button>
        </section>
    </main>
</body>
```

CSS：

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    min-height: 100vh;
    font-family: Arial, sans-serif;
    background-color: #f5f5f5;
}

header {
    text-align: center;
    padding: 20px;
}

.game-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
}

canvas {
    border: 2px solid black;
    background-color: white;
}

.controls {
    display: flex;
    gap: 10px;
}

button {
    padding: 10px 16px;
    border: none;
    border-radius: 6px;
    cursor: pointer;
}

button:hover {
    transform: translateY(-2px);
}
```

这个例子中已经使用了：

```text
盒模型
Flex
gap
border
background
padding
hover
transform
```

---

## 40. Flex 常用速查

```css
.container {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 20px;
}
```

作用：

| 属性 | 作用 |
| --- | --- |
| `display: flex` | 开启 Flex |
| `flex-direction` | 设置主轴方向 |
| `justify-content` | 主轴对齐 |
| `align-items` | 交叉轴对齐 |
| `flex-wrap` | 是否换行 |
| `gap` | 子元素间距 |

---

## 41. Grid 常用速查

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

作用：

| 属性 | 作用 |
| --- | --- |
| `display: grid` | 开启 Grid |
| `grid-template-columns` | 定义列 |
| `grid-template-rows` | 定义行 |
| `gap` | 行列间距 |
| `1fr` | 一份可用空间 |

---

## 42. 常用 CSS 属性速查表

| 属性 | 作用 |
| --- | --- |
| `color` | 文字颜色 |
| `background-color` | 背景颜色 |
| `font-size` | 字体大小 |
| `font-weight` | 字体粗细 |
| `font-family` | 字体 |
| `text-align` | 文本对齐 |
| `width` | 宽度 |
| `height` | 高度 |
| `margin` | 外边距 |
| `padding` | 内边距 |
| `border` | 边框 |
| `border-radius` | 圆角 |
| `box-shadow` | 阴影 |
| `display` | 显示方式 |
| `position` | 定位方式 |
| `top/right/bottom/left` | 定位偏移 |
| `z-index` | 层级 |
| `overflow` | 溢出处理 |
| `opacity` | 透明度 |
| `cursor` | 鼠标样式 |
| `gap` | 元素间距 |
| `transition` | 过渡动画 |
| `transform` | 移动、缩放、旋转 |
| `animation` | 动画 |
| `justify-content` | Flex/Grid 主轴对齐 |
| `align-items` | Flex/Grid 交叉轴对齐 |
| `grid-template-columns` | Grid 列布局 |

---

## 43. 初学阶段重点掌握

建议学习顺序：

```text
CSS 基本语法
↓
标签 / class / id 选择器
↓
颜色、字体、背景
↓
width / height
↓
margin / padding / border
↓
盒模型
↓
display
↓
Flex
↓
position
↓
Grid
↓
hover / transition / transform
↓
响应式设计
↓
CSS 优先级和继承
```

其中最重要的几个知识点是：

```text
选择器
盒模型
Flex
position
Grid
响应式
优先级
```

如果这些掌握得比较牢，已经能够完成大多数基础网页布局。

---

## 44. CSS 学习时需要建立的核心认识

学习 CSS 时不要只记属性，而要理解网页布局的几个核心问题：

```text
这个元素多大？
→ width / height

它和其他元素距离多少？
→ margin / padding / gap

它怎么排列？
→ block / flex / grid

它在哪里？
→ position

它长什么样？
→ color / background / border / shadow

鼠标交互时怎么变化？
→ hover / transition / transform

不同屏幕怎么办？
→ responsive / media query
```

理解这套思路后，遇到一个网页界面时，就可以逐层分析应该使用哪些 CSS 属性。
