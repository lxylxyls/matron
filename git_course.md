# 安装git

```c
https://www.git-scm.com/download/win
```

下载好后所有选项都默认，如需更改配置环境变量时候更改为相应配置

# 配置环境变量

在Path中配置环境变量，默认安装路径

```c
C:\Program Files\Git\bin
C:\Program Files\Git\mingw64\bin
C:\Program Files\Git\mingw64\libexec\git-core
```

# 用户配置

用户名配置

```c
git config --global user.name 'damer'
```

邮箱配置

```c
 git config --global user.email '。。。。。@qq.com'
```

# 仓库创建

选择一个本地文件夹作为仓库目录 cd 到该目录下

```c
git init
```

# 提交缓存

```c
git add 文件名
```

# 向仓库提交缓存

```c
git commit -m '描述必填'
```

# 链接远程仓库

链接指来至gtee、github的仓库链接

```c
git remote add 别名 链接
//修改别名
git remote rename 旧名 新名
```

# 查看链接库

```c
git remote
```

# 提交到远程仓库

```c
git push -u 别名 分支名
```

# 从仓库同步文件

```c
git pull 别名 分支名
```

# 查看分支

```c
git branch -a
```

# 切换分支

当上传或者更新时，与远程仓库产生冲突时，可以先查看本地分支是否与远程分支相同，不同则用以下命令即可

```c
git checkout 分支名
```

# 删除分支

```c
git branch -d 分支名
```

# 创建分支

```c
git branch -b 分支名
```

# 合并分支

切换到主分支再执行该命令合并分支

```c
git merge 分支名
```

# 删除远程分支

```c
git push 别名 --delete 远程分支名
```

# 删除仓库中的文件

```c
git rm -r 文件名
```

执行该命令后需要 git commit -m ' ' 提交代码

然后git push 别名 分支名 远程更新代码

# 增加忽略文件

创建一个*.ignore文件\*代表任意命名

编辑器打开该文件，写入需要忽略的文件名

如：

```c
*.txt

test.c

//找到隐藏文件.git 中的config 

[core]

excludesfile=.ignore路径 windows中路径\换成/
```

已经上传的文件需要git rm -r 删除后再更新同步

