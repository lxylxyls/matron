# 用户配置

用户名配置

```c
git config --global user.name 'damer'
```

邮箱配置

```c
 git config --global user.email '403375160@qq.com'
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

```c
git remote add 别名 链接
//修改别名
git remote rename 旧名 新名
```

# 提交到远程仓库

```c
git push 别名 master
```

