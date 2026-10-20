# HTML 知识点整理

## 1. HTML 是什么

HTML（HyperText Markup Language，超文本标记语言）用于描述网页的结构和内容。HTML 本身不是编程语言，而是一种标记语言，通过不同标签告诉浏览器“这里是什么内容”。

一个网页通常由三部分组成：

| 技术 | 主要作用 |
| --- | --- |
| HTML | 定义网页结构和内容 |
| CSS | 控制网页样式和布局 |
| JavaScript | 实现网页交互和逻辑 |

可以简单理解为：**HTML 决定网页有什么，CSS 决定网页长什么样，JavaScript 决定网页会做什么。**

---

## 2. HTML 基本结构

一个最基本的 HTML 文件如下：

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的网页</title>
</head>
<body>
    <h1>Hello HTML</h1>
    <p>这是我的第一个网页。</p>
</body>
</html>
```

各部分含义：

| 代码                       | 含义                   |
| ------------------------ | -------------------- |
| `<!DOCTYPE html>`        | 告诉浏览器当前文档使用 HTML5    |
| `<html>`                 | 整个 HTML 文档的根元素       |
| `<head>`                 | 保存网页配置、标题、编码、CSS 等信息 |
| `<meta charset="UTF-8">` | 设置字符编码为 UTF-8        |
| `<meta name="viewport">` | 控制移动端页面缩放和宽度         |
| `<title>`                | 浏览器标签页显示的标题          |
| `<body>`                 | 浏览器页面中真正显示的内容        |

---

## 3. HTML 标签与元素

HTML 标签一般成对出现：

```html
<p>Hello</p>
```

其中：

```text
<p>      开始标签
Hello    内容
</p>     结束标签
```

整个 `<p>Hello</p>` 称为一个 HTML 元素。

有些标签不需要结束标签，例如：

```html
<img src="photo.png" alt="图片">
<br>
<hr>
<input type="text">
```

---

## 4. 标题与文本标签

### 4.1 标题

HTML 提供六级标题：

```html
<h1>一级标题</h1>
<h2>二级标题</h2>
<h3>三级标题</h3>
<h4>四级标题</h4>
<h5>五级标题</h5>
<h6>六级标题</h6>
```

`<h1>` 级别最高，通常用于页面主标题。

### 4.2 段落

```html
<p>这是一个段落。</p>
```

### 4.3 换行

```html
第一行<br>第二行
```

### 4.4 水平线

```html
<hr>
```

### 4.5 强调文字

```html
<strong>重要内容</strong>
<em>强调内容</em>
```

`<strong>` 通常显示为粗体，`<em>` 通常显示为斜体，但它们更重要的意义是表达语义。

---

## 5. 链接

使用 `<a>` 创建超链接：

```html
<a href="https://example.com">访问网站</a>
```

常用属性：

```html
<a href="https://example.com" target="_blank">新窗口打开</a>
```

| 属性 | 含义 |
| --- | --- |
| `href` | 链接目标地址 |
| `target="_blank"` | 在新标签页打开链接 |

也可以链接到本地页面：

```html
<a href="about.html">关于我们</a>
```

---

## 6. 图片

使用 `<img>` 显示图片：

```html
<img src="images/photo.jpg" alt="风景照片">
```

常用属性：

| 属性 | 含义 |
| --- | --- |
| `src` | 图片文件地址 |
| `alt` | 图片无法显示时的替代文字 |
| `width` | 图片宽度 |
| `height` | 图片高度 |

例如：

```html
<img src="logo.png" alt="网站 Logo" width="200">
```

---

## 7. 列表

### 7.1 无序列表

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```

### 7.2 有序列表

```html
<ol>
    <li>安装编辑器</li>
    <li>创建 HTML 文件</li>
    <li>打开浏览器</li>
</ol>
```

其中 `<li>` 表示列表项。

---

## 8. 常用语义化结构元素

HTML5 提供了一些具有明确语义的结构标签。

### 8.1 `header`

表示页面或某个区域的头部，通常放标题、Logo、导航栏等：

```html
<header>
    <h1>我的网站</h1>
</header>
```

### 8.2 `nav`

表示导航区域：

```html
<nav>
    <a href="/">首页</a>
    <a href="/about.html">关于</a>
</nav>
```

### 8.3 `main`

表示页面最主要的内容：

```html
<main>
    <h2>主要内容</h2>
</main>
```

一个页面通常只有一个主要的 `<main>`。

### 8.4 `section`

表示一个具有独立主题的内容区域：

```html
<section>
    <h2>产品介绍</h2>
    <p>这里是产品介绍。</p>
</section>
```

### 8.5 `article`

表示可以独立存在的一篇内容，例如文章、帖子、新闻：

```html
<article>
    <h2>新闻标题</h2>
    <p>新闻正文。</p>
</article>
```

### 8.6 `footer`

表示页面或区域底部：

```html
<footer>
    <p>Copyright 2026</p>
</footer>
```

一个常见页面结构如下：

```html
<body>
    <header>
        <h1>网站标题</h1>
        <nav>导航栏</nav>
    </header>

    <main>
        <section>
            <h2>第一部分</h2>
        </section>

        <section>
            <h2>第二部分</h2>
        </section>
    </main>

    <footer>
        <p>页脚</p>
    </footer>
</body>
```

---

## 9. `div` 和 `span`

### 9.1 `div`

`<div>` 是通用块级容器，本身没有特殊语义，常用于布局和 CSS 样式控制：

```html
<div class="card">
    <h2>标题</h2>
    <p>内容</p>
</div>
```

### 9.2 `span`

`<span>` 是通用行内容器，经常用于给一小段文字添加样式：

```html
<p>价格：<span class="price">99 元</span></p>
```

可以简单理解：

```text
div  → 包住一大块内容
span → 包住一小段行内内容
```

---

## 10. HTML 属性

属性写在开始标签中：

```html
<a href="https://example.com" target="_blank">链接</a>
```

基本格式：

```html
<tag 属性名="属性值">内容</tag>
```

常见通用属性：

| 属性 | 作用 |
| --- | --- |
| `id` | 给元素设置唯一标识 |
| `class` | 给一个或多个元素设置分类名称 |
| `style` | 直接写 CSS 样式 |
| `title` | 鼠标悬停时显示提示文字 |

例如：

```html
<p id="intro" class="text">Hello</p>
```

---

## 11. `id` 与 `class`

`id` 通常用于唯一元素：

```html
<h1 id="title">网站标题</h1>
```

`class` 可以被多个元素重复使用：

```html
<p class="warning">警告 1</p>
<p class="warning">警告 2</p>
```

CSS 中对应写法：

```css
#title {
    color: blue;
}

.warning {
    color: red;
}
```

其中：

```text
# 表示 id
. 表示 class
```

---

## 12. 按钮

使用 `<button>` 创建按钮：

```html
<button>点击我</button>
```

按钮经常配合 JavaScript：

```html
<button id="btn">点击我</button>
```

```javascript
document.getElementById("btn").addEventListener("click", function () {
    alert("按钮被点击了");
});
```

---

## 13. 表单

表单用于收集用户输入。

### 13.1 基本表单

```html
<form>
    <label for="username">用户名：</label>
    <input id="username" type="text">

    <button type="submit">提交</button>
</form>
```

### 13.2 常见 `input` 类型

```html
<input type="text">
<input type="password">
<input type="email">
<input type="number">
<input type="date">
<input type="checkbox">
<input type="radio">
<input type="file">
<input type="submit">
```

常见属性：

| 属性 | 含义 |
| --- | --- |
| `type` | 输入框类型 |
| `name` | 提交数据时使用的字段名 |
| `value` | 输入框的值 |
| `placeholder` | 输入提示文字 |
| `required` | 必填 |
| `disabled` | 禁用 |
| `checked` | 默认选中 |

例如：

```html
<input type="text" name="username" placeholder="请输入用户名" required>
```

### 13.3 多行文本

```html
<textarea rows="5" cols="40"></textarea>
```

### 13.4 下拉选择

```html
<select name="city">
    <option value="shanghai">上海</option>
    <option value="beijing">北京</option>
</select>
```

---

## 14. 表格

基本表格：

```html
<table>
    <thead>
        <tr>
            <th>姓名</th>
            <th>年龄</th>
        </tr>
    </thead>

    <tbody>
        <tr>
            <td>张三</td>
            <td>20</td>
        </tr>
    </tbody>
</table>
```

常见标签：

| 标签 | 含义 |
| --- | --- |
| `<table>` | 表格 |
| `<thead>` | 表头区域 |
| `<tbody>` | 表格主体 |
| `<tr>` | 一行 |
| `<th>` | 表头单元格 |
| `<td>` | 普通单元格 |

---

## 15. 音频与视频

### 15.1 音频

```html
<audio src="music.mp3" controls></audio>
```

### 15.2 视频

```html
<video src="video.mp4" controls width="640"></video>
```

`controls` 表示显示播放、暂停、音量等控制按钮。

---

## 16. `canvas`

`<canvas>` 是 HTML 提供的绘图区域，本身只是一个画布，真正绘图通常需要 JavaScript。

```html
<canvas id="myCanvas" width="400" height="300"></canvas>
```

JavaScript：

```javascript
const canvas = document.getElementById("myCanvas");
const ctx = canvas.getContext("2d");

ctx.fillRect(50, 50, 100, 100);
```

`canvas` 常用于：

- 图形绘制
- 数据可视化
- 动画
- 小游戏
- 图片处理

---

## 17. 引入 CSS

推荐将 CSS 单独写在 `.css` 文件中。

目录：

```text
project/
├── index.html
└── style.css
```

HTML 中使用 `<link>` 引入：

```html
<head>
    <link rel="stylesheet" href="style.css">
</head>
```

其中：

```text
rel="stylesheet" → 表示引入的是样式表
href="style.css" → CSS 文件的位置
```

也可以直接在 HTML 中写 CSS：

```html
<style>
    h1 {
        color: red;
    }
</style>
```

或者使用行内样式：

```html
<h1 style="color: red;">Hello</h1>
```

一般大型项目更推荐使用独立 CSS 文件。

---

## 18. 引入 JavaScript

目录：

```text
project/
├── index.html
└── main.js
```

HTML 中使用 `<script>`：

```html
<script src="main.js"></script>
```

现代网页常见写法：

```html
<head>
    <script src="main.js" defer></script>
</head>
```

`defer` 表示浏览器解析 HTML 时可以同时下载 JavaScript，但会等 HTML 解析完成后再执行 JavaScript。

也可以直接在 HTML 中写 JavaScript：

```html
<script>
    console.log("Hello JavaScript");
</script>
```

---

## 19. 文件路径

假设目录如下：

```text
project/
├── index.html
├── css/
│   └── style.css
├── js/
│   └── main.js
└── images/
    └── logo.png
```

在 `index.html` 中：

```html
<link rel="stylesheet" href="css/style.css">
<script src="js/main.js" defer></script>
<img src="images/logo.png" alt="Logo">
```

### 19.1 当前目录

```text
./
```

例如：

```html
<img src="./logo.png" alt="Logo">
```

### 19.2 上一级目录

```text
../
```

例如当前文件在：

```text
pages/about.html
```

图片在：

```text
images/logo.png
```

可以写：

```html
<img src="../images/logo.png" alt="Logo">
```

---

## 20. 注释

HTML 注释：

```html
<!-- 这是 HTML 注释 -->
```

CSS 注释：

```css
/* 这是 CSS 注释 */
```

JavaScript 注释：

```javascript
// 单行注释

/*
多行注释
*/
```

---

## 21. 块级元素与行内元素

块级元素一般独占一行，例如：

```html
<div></div>
<p></p>
<h1></h1>
<section></section>
```

行内元素通常与其他内容处于同一行，例如：

```html
<span></span>
<a></a>
<strong></strong>
<em></em>
```

不过最终显示方式也可以通过 CSS 的 `display` 属性改变，因此不要把“块级”和“行内”理解为绝对不可改变。

---

## 22. HTML 实体

有些字符在 HTML 中具有特殊意义，需要使用实体表示。

| 显示字符 | HTML |
| --- | --- |
| `<` | `&lt;` |
| `>` | `&gt;` |
| `&` | `&amp;` |
| 空格 | `&nbsp;` |
| `©` | `&copy;` |

例如：

```html
<p>3 &lt; 5</p>
```

显示为：

```text
3 < 5
```

---

## 23. 常见网页完整示例

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>个人主页</title>
    <link rel="stylesheet" href="style.css">
    <script src="main.js" defer></script>
</head>

<body>
    <header>
        <h1>我的个人主页</h1>

        <nav>
            <a href="#about">关于我</a>
            <a href="#skills">技能</a>
            <a href="#contact">联系我</a>
        </nav>
    </header>

    <main>
        <section id="about">
            <h2>关于我</h2>
            <p>这里是个人介绍。</p>
        </section>

        <section id="skills">
            <h2>技能</h2>

            <ul>
                <li>HTML</li>
                <li>CSS</li>
                <li>JavaScript</li>
            </ul>
        </section>

        <section id="contact">
            <h2>联系我</h2>

            <form>
                <label for="name">姓名：</label>
                <input id="name" type="text" required>

                <button type="submit">提交</button>
            </form>
        </section>
    </main>

    <footer>
        <p>Copyright 2026</p>
    </footer>
</body>
</html>
```

---

## 24. 推荐的项目目录结构

初学阶段可以使用：

```text
project/
├── index.html
├── css/
│   └── style.css
├── js/
│   └── main.js
├── images/
│   └── logo.png
└── assets/
```

稍大的项目可以继续按照页面、组件和静态资源分类。

---

## 25. HTML 编写规范

建议遵循以下习惯：

1. 标签尽量正确闭合。
2. 使用清晰统一的缩进，通常使用 2 个或 4 个空格。
3. 标签名和属性名通常全部小写。
4. 属性值使用双引号。
5. 图片尽量填写 `alt`。
6. 优先使用具有语义的标签，如 `header`、`main`、`section`、`article`、`footer`。
7. 不要为了布局滥用 `<br>`。
8. CSS 尽量放在独立 `.css` 文件中。
9. JavaScript 尽量放在独立 `.js` 文件中。
10. 文件和目录名称尽量使用英文、小写和短横线，例如 `user-profile.html`。

---

## 26. HTML、CSS、JavaScript 的关系

例如：

### HTML

```html
<button id="btn">点击我</button>
```

### CSS

```css
#btn {
    background: black;
    color: white;
}
```

### JavaScript

```javascript
const btn = document.getElementById("btn");

btn.addEventListener("click", function () {
    alert("Hello");
});
```

三者关系：

```text
HTML
↓
创建按钮

CSS
↓
修改按钮外观

JavaScript
↓
定义按钮被点击后发生什么
```

---

## 27. 初学阶段重点掌握

建议优先掌握：

```text
HTML 基本结构
↓
标题、段落、链接、图片、列表
↓
div、span
↓
header、nav、main、section、footer
↓
id、class、常用属性
↓
表单 input / button / form
↓
CSS 的 link 引入
↓
JavaScript 的 script 引入
↓
相对路径
↓
完整网页结构
```

不需要一开始记住所有标签，重点是理解 HTML 的核心思想：**通过标签表达网页内容的结构和语义。**

---

## 28. 常用标签速查表

| 标签 | 作用 |
| --- | --- |
| `<html>` | HTML 文档根元素 |
| `<head>` | 网页配置区域 |
| `<body>` | 页面显示内容 |
| `<title>` | 浏览器标签页标题 |
| `<h1>` ~ `<h6>` | 标题 |
| `<p>` | 段落 |
| `<a>` | 超链接 |
| `<img>` | 图片 |
| `<ul>` | 无序列表 |
| `<ol>` | 有序列表 |
| `<li>` | 列表项 |
| `<div>` | 通用块级容器 |
| `<span>` | 通用行内容器 |
| `<header>` | 头部区域 |
| `<nav>` | 导航区域 |
| `<main>` | 主体内容 |
| `<section>` | 内容分区 |
| `<article>` | 独立文章内容 |
| `<footer>` | 页脚 |
| `<form>` | 表单 |
| `<input>` | 输入框 |
| `<textarea>` | 多行输入框 |
| `<select>` | 下拉框 |
| `<button>` | 按钮 |
| `<table>` | 表格 |
| `<audio>` | 音频 |
| `<video>` | 视频 |
| `<canvas>` | 绘图画布 |
| `<link>` | 引入外部资源，最常见为 CSS |
| `<script>` | 引入或编写 JavaScript |
| `<meta>` | 网页元数据 |
| `<br>` | 换行 |
| `<hr>` | 水平分隔线 |
