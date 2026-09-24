---
date: 2026-09-17
tags:
  - docker
  - spring
  - spring-boot
  - labelme
---
# Labelme
1. 准备需要标注的文件夹, images/
2. 准备**labels.txt**
```
__ignore__
_background_
```
```
label
```
..
|--images/
|--labels.txt
3. 父目录激活labelme虚拟环境, 输入以下命令
```
labelme images --labels labels.txt --nodata --validatelabel exact --config '[shift_auto_shape_color:-2}'
``` 
# Docker
相当于虚拟机, 用于在服务器快速部署应用程序
Docker Desktop
# Spring
Jave框架
# Spring Boot
快速部署spring
# CMD
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


