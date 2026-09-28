---
date: 2026-09-22
tags:
  - SSH
  - Git
  - GitHub
  - Markdown
  - Docker
  - Spring
  - Spring-Boot
  - Labelme
---
# Dev Cheatsheet

## SSH

需要自己电脑生成一对公钥和私钥。

1. `ls -al ~/.ssh` 查看本地 SSH 配置
2. `ssh-keygen -t ed25519 -C "邮箱"` 生成 SSH 密钥
3. `cat ~/.ssh/id_ed25519.pub` 查看公钥
4. 在 GitHub 中添加 SSH 公钥
5. `ssh -T git@github.com` 测试 SSH 是否配置成功
6. `git clone git@github.com:Berkeley-CS61B/library-sp26.git` 使用 SSH 克隆仓库

如果已经通过 HTTPS 克隆过仓库，不需要重新 clone，可以直接修改远程地址：

```bash
git remote set-url origin git@github.com:用户名/仓库名.git
```

## Git

1. `git init` 初始化 Git 仓库
2. `git remote add origin git@github.com:username/hw01.git`
   `git remote set-url origin git@github.com:Marin-OVO/CS61A.git`
3. `git log --oneline --all --graph --decorate`
   `git status`
   查看日志
4. `git checkout branchname`
   `git switch branchname`
   切换分支
5. `git switch --detach 哈希表ID`
   切换旧分支

### Git -> GitHub

1. `git status` 检查是否存在任何未同步的更改
2. `git add hw01/src/Arithmetic.java` 告诉 Git 该追踪什么文件
3. `git commit -m "fixed Arithmetic.java in hw01"` 截取更改快照并附上注释
4. 在 GitHub 上创建仓库，并且执行 `git remote add origin`
5. `git branch --show-current` 检查当前分支名
   `git branch -M main`
6. `git push origin main` 将本地快照上传 GitHub（将本地 origin 分支上传到 GitHub 的 main 分支）

### GitHub -> Git

1. 第一次把整个远程仓库复制到本地：
   `git clone https/ssh`
2. 本地已有这个仓库了，把远程的新变化拉下来：
   `git pull origin main` 远程仓库的 main 分支
3. `git fetch origin main` 查看远程仓库情况
   `git diff HEAD origin/main`
   `git merge origin/main`

## Markdown

| Markdown               | 含义      |
| ---------------------- | ------- |
| `$\sum$`               | 求和      |
| `$\sum_{i=1}^{n} x_i$` | 带上下限的求和 |
| `$\prod$`              | 连乘      |
| `$\int$`               | 积分      |
| `$\infty$`             | 无穷      |
| `$\sqrt{x}$`           | 根号      |
| `$\frac{a}{b}$`        | 分数      |
| `$x^2$`                | 上标      |
| `$x_i$`                | 下标      |
| `$\alpha$`             | α       |
| `$\beta$`              | β       |
| `$\theta$`             | θ       |
| `$\pi$`                | π       |
| `$\leq$`               | ≤       |
| `$\geq$`               | ≥       |
| `$\neq$`               | ≠       |
| `$\approx$`            | ≈       |
| `$\in$`                | ∈       |
| `$\notin$`             | ∉       |
| `$\rightarrow$`        | →       |

```math
F_1 = \frac{2PR}{P+R}
```

## Labelme

1. 准备需要标注的文件夹 `images/`
2. 准备 **labels.txt**

```text
__ignore__
_background_

label
```

目录结构：

```text
.
├── images/
└── labels.txt
```

3. 父目录激活 Labelme 虚拟环境，输入以下命令：

```bash
labelme images --labels labels.txt --nodata --validate-label exact --config "{shift_auto_shape_color: -2}"
```

## Docker

相当于虚拟机，用于在服务器快速部署应用程序。

`Docker Desktop`

## Spring

Java 框架。

### Spring Boot

快速部署 Spring。

## CMD

**dir**  
**cd**  
**copy**

```shell
mkdir newdir
copy 175.png .\newdir\
copy 365.png .\newdir\
copy 205.png .\newdir\
copy 296.png .\newdir\
copy 693.png .\newdir\

copy *_175.png .\newdir\
copy *_365.png .\newdir\
copy *_205.png .\newdir\
copy *_296.png .\newdir\
copy *_693.png .\newdir\
```

**del**  
**mkdir**

```shell
# 设置项目路径
set PYTHONPATH=%CD%;%PYTHONPATH%
```
