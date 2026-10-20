---
date: 2026-09-30
tags:
  - HTML
  - CSS
  - JavaScript
---
# 项目总览
snake-game/
├── index.html
├── styles.css
├── app.js
└── README.md
# 1. 引入CSS和JavaScript
```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
	
	<!-- CSS -->
    <link rel="stylesheet" href="style.css">
</head>

<!-- HTML -->
<body>
    <h1>Hello</h1>
	
	<!-- JS -->
    <script src="main.js"></script> 
</body>
</html>
```
# 2. 设计HTML
```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <!-- 自适应设备屏幕 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Snake Game</title>
    <link rel="stylesheet" href="styles.css">
</head>

<body>
    <header>
        <h1 class="gameTitle">Snake Game</h1>

        <section>
            <button id="startButton">开始游戏</button>
            <button id="pauseButton">暂停游戏</button>
            <button id="restartButton">重新开始</button>
            <button id="instructionsButton">操作说明</button>
        </section>

        <div class="score">
            <span>当前分数：0</span>
            <span>最高分数：0</span>
        </div>
    </header>

    <main>
        <canvas id="myCanvas" width="400" height="300"></canvas>
    </main>

    <script src="app.js"></script>
</body>
</html>
```
# 3. 设计CSS
```CSS
/* 标签选择器 */
body {
    margin: 0;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #f4f4f4;
    font-family: Arial, sans-serif;
}

header {
    /* 只表示内容的宽度 */
    width: 400px;
    text-align: center;
    margin-top: 30px;
}

header section {
    display: flex;
    justify-content: center;
    gap: 10px;
    margin-bottom: 20px;
}

button {
    padding: 8px 14px;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    font-size: 14px;
    background-color: rgb(219, 218, 218);
}

/* 鼠标悬停, 改变颜色 */
button:hover {
    opacity: 0.8;
    background-color: black;
    color: white;
}

main {
    display: flex;
    justify-content: center;
}

/* 类选择器 */
.gameTitle {
    margin-bottom: 20px;
    font-size: 36px;
}

.score {
    display: flex;
    justify-content: space-between;
    margin-bottom: 15px;
    font-size: 16px;
    font-weight: bold;
}

/* ID选择器 */
#myCanvas {
    border: 2px solid #333;
    background-color: white;
}
```

margin -> border -> padding -> content

# 4. 适配各种大小屏幕
```CSS
body {
    margin: 0;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #f4f4f4;
    font-family: Arial, sans-serif;
    padding: 20px;
    box-sizing: border-box;
}

header {
    width: 100%;
    max-width: 400px;
    text-align: center;
    margin-top: 30px;
}

header section {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 20px;
}

button {
    padding: 8px 14px;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    font-size: 14px;
    background-color: rgb(219, 218, 218);
}

button:hover {
    opacity: 0.8;
    background-color: black;
    color: white;
}

main {
    width: 100%;
    display: flex;
    justify-content: center;
}

.gameTitle {
    margin-bottom: 20px;
    font-size: 36px;
}

.score {
    display: flex;
    justify-content: space-between;
    gap: 20px;
    margin-bottom: 15px;
    font-size: 16px;
    font-weight: bold;
}

#myCanvas {
    width: 100%;
    max-width: 400px;
    height: auto;
    border: 2px solid #333;
    background-color: white;
}
```