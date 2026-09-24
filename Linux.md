---
date: 2026-09-23
tags:
  - Linux
  - Shell
---
# Linux
## Shell
常见 Shell：
```bash
sh
bash
zsh
```
查看当前 Shell：
```bash
echo $SHELL
```
## 环境变量
### `$HOME`
当前用户家目录：
```bash
echo $HOME
cd ~
```
### `$PATH`
Shell 查找可执行程序的路径：
```bash
echo $PATH
which python
which git
```
### `$SHELL`
当前用户默认 Shell：
```bash
echo $SHELL
```
设置环境变量：
```bash
export NAME=value
export CUDA_VISIBLE_DEVICES=0
```
## 文件系统
```text
/               根目录
/home           用户目录
/home/marin     用户家目录
/etc            系统配置
/usr            软件和程序
/bin            常用命令
/tmp            临时文件
```
## 路径
```text
/      根目录
~      用户家目录
.      当前目录
..     上一级目录
```
```bash
pwd             # 当前路径
cd dir          # 进入目录
cd ..           # 上一级
cd ~            # 家目录
cd -            # 上一次目录
```
## ls
```bash
ls              # 查看目录
ls -l           # 详细信息
ls -a           # 包含隐藏文件
ls -la          # 详细信息+隐藏文件
```
## 文件与目录
```bash
mkdir test              # 创建目录
mkdir -p a/b/c          # 递归创建目录
touch test.txt          # 创建空文件
cp a.txt b.txt          # 复制文件
cp -r dir1 dir2         # 复制目录
mv old.txt new.txt      # 移动/重命名
rm test.txt             # 删除文件
rm -r folder            # 删除目录
rm -rf folder           # 强制递归删除
```
## 查看文件
```bash
cat file.txt            # 输出整个文件
less file.txt           # 分页查看
head file.txt           # 前10行
head -n 20 file.txt     # 前20行
tail file.txt           # 后10行
tail -n 20 file.txt     # 后20行
tail -f train.log       # 实时查看日志
```
## echo
```bash
echo hello
echo $HOME
echo "hello" > file.txt     # 覆盖写入
echo "hello" >> file.txt    # 追加写入
```
## grep
按行搜索文本：
```bash
grep [选项] "模式" 文件
```
```bash
grep "text" file          # 搜索
grep -i "text" file       # 忽略大小写
grep -n "text" file       # 显示行号
grep -v "text" file       # 反选
grep -r "text" dir        # 递归搜索目录
grep -rn "text" .         # 当前目录递归搜索+行号
command | grep "text"     # 过滤其他命令输出
```
例如：
```bash
grep -rn "learning_rate" .
ps aux | grep python
```
## find
```bash
find . -name "*.txt"          # 查找txt
find . -name "*.py"           # 查找Python文件
find . -type f                # 只找文件
find . -type d                # 只找目录
find . -type f -mtime +30     # 30天前修改的文件
```
## Glob
```text
*       任意数量字符
?       任意一个字符
[]      字符集合
{}      多个候选
```
```bash
ls *.txt
ls file?.txt
ls {a,b,c}.txt
```
## 重定向
```bash
command > file        # 覆盖输出
command >> file       # 追加输出
command < input.txt   # 文件作为输入
```
## 管道
```bash
command1 | command2
```
例如：
```bash
ps aux | grep python
```
表示：
```text
ps aux → 所有进程 → grep python → 只保留Python相关行
```
## 命令组合
```bash
command1 ; command2     # 无论前一个是否成功都执行
command1 && command2    # 前一个成功才执行
command1 || command2    # 前一个失败才执行
```
例如：
```bash
mkdir test && cd test
```
## 权限
```text
r = read    读
w = write   写
x = execute 执行
```
```bash
ls -l
chmod +x script.sh
chmod 755 script.sh
```
```text
r = 4
w = 2
x = 1
```
`755`：
```text
owner   rwx = 7
group   r-x = 5
others  r-x = 5
```
## sudo
管理员权限：
```bash
sudo command
sudo apt update
```
## apt
Ubuntu/Debian 软件管理：
```bash
sudo apt update
sudo apt install git
sudo apt remove git
apt search python
```
## 进程
```bash
ps                      # 当前进程
ps aux                  # 所有进程
ps aux | grep python    # 查Python进程
top                     # 实时查看
htop                    # 更友好的实时查看
kill PID                # 结束进程
kill -9 PID             # 强制结束
```
## 后台任务
```bash
python train.py &       # 后台运行
jobs                    # 查看后台任务
bg                      # 放到后台
fg                      # 切回前台
```
## 快捷键
```text
Ctrl+C    中断程序
Ctrl+D    EOF/退出Shell
Ctrl+L    清屏
Ctrl+A    移到行首
Ctrl+E    移到行尾
Ctrl+R    搜索历史命令
```
## history
```bash
history
history | grep git
!!                      # 执行上一条命令
```
## which
查找程序路径：
```bash
which python
which git
which gcc
```
## type
查看命令类型：
```bash
type cd
type ls
type python
```
可判断是：
```text
Shell builtin
alias
可执行文件
```
## alias
```bash
alias ll='ls -la'
```
之后：
```bash
ll
```
等价于：
```bash
ls -la
```
## Shell脚本
```bash
#!/bin/bash
echo "Hello Linux"
```
运行：
```bash
chmod +x test.sh
./test.sh
```
或者：
```bash
bash test.sh
```
## Shell变量
```bash
name="Marin"
echo $name
echo ${name}
```
注意：
```bash
name = "Marin"   # 错误，=两边不能有空格
```
## 条件
```bash
if [ -f test.txt ]; then
    echo "file exists"
fi
```
## 循环
```bash
for file in *.txt
do
    echo "$file"
done
```
```bash
while condition
do
    command
done
```
## 网络
```bash
ip addr                 # 查看IP
ping github.com         # 测试连通
curl https://example.com
wget URL
ss -tulpn               # 查看端口
```
## 磁盘
```bash
df -h           # 磁盘空间
du -sh folder   # 目录大小
du -sh *        # 当前目录各文件大小
```
## 压缩
```bash
tar -cvf files.tar folder/       # 打包
tar -xvf files.tar               # 解包
tar -czvf files.tar.gz folder/   # gzip压缩
tar -xzvf files.tar.gz           # 解压
zip -r files.zip folder/
unzip files.zip
```
## Git
```bash
git status
git add .
git commit -m "message"
git push
git pull
git log --oneline
```
## Python虚拟环境
```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python main.py
```
## 常用命令速查
```bash
pwd                     # 当前路径
ls                      # 查看文件
ls -la                   # 详细信息+隐藏文件
cd dir                  # 进入目录
cd ..                   # 上一级
cd ~                    # 家目录
mkdir dir               # 创建目录
touch file              # 创建文件
cp a b                  # 复制
cp -r a b               # 复制目录
mv a b                  # 移动/重命名
rm file                 # 删除文件
rm -r dir               # 删除目录
cat file                # 查看文件
less file               # 分页查看
head file               # 查看开头
tail file               # 查看结尾
tail -f log.txt         # 实时日志
grep "text" file        # 搜索
grep -rn "text" .       # 递归搜索
find . -name "*.py"     # 查找文件
echo $PATH              # 查看PATH
which python            # 查程序路径
ps aux                  # 查看进程
ps aux | grep python    # 查Python进程
kill PID                # 结束进程
chmod +x script.sh      # 添加执行权限
command1 | command2     # 管道
command > file          # 覆盖输出
command >> file         # 追加输出
```
