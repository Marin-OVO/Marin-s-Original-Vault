# SSH
需要自己电脑生成一对公钥和私钥
1. ls -al ~/.ssh 查看本地ssh配置
2. ssh-kengen -t ed25519 -C "邮箱"
3. cat ~/.ssh/id_ed25519.pub 查看公钥
4. 在github中添加ssh公钥
5. ssh -T git@github.com
6. git clone git@github.com:Berkeley-CS61B/library-sp26.git 运行
# Git
1. git init 初始化git仓库
2. git remote add origin git@github.com:username/hw01.git
# Git -> Github
1. git status 检查是否存在任何未同步的更改
2. git add hw01/src/Arithmetic.java 告诉git该追踪什么文件
3. git commit -m "fixed Arithmetic.java in hw01" 截取更改快照并附上注释
4. (在github上创建仓库, 并且git remote add origin)
5. git push origin main 将本地快照上传github(将本地origin分支上传到github的main分支)
