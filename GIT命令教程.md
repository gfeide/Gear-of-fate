# Git命令指南

## 1、Git工作流程

自己创建编写对的文件时工作区，在此编写代码，这个文件会上传到暂存区，紧接着会上传到本地仓库，也是可以随时取消。最后是可以把代码吗上传到远程仓库，分享供大家使用。

![工作区](D:\桌面\Git本地仓库\img\工作区.png)

## 2、Git快速入门

1、在本地工作区创建文件：

```shell
[root@git data]# mkdir file{1..3}.txt
[root@git data]# ls
[root@git data]# file1.txt file2.txt file3.txt
```

2、查看工作区文件状态：

格式：git status

3、**提交工作区文件到暂存区**（所有的项目文件都需要经过暂存区才可以提交到git仓库中）

格式：git add 文件名  （提交所有文件 git add . 或者 git add *）

```shell
[root@ali_cloud git_data]# git add file3
[root@ali_cloud git_data]# git status
 On branch master
Changes to be committed:
(use "git reset HEAD <file>..." to unstage)

       new file:   file3

Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git checkout -- <file>..." to discard changes in working directory)

     modified:   guess_number.py

```

​    **将文件从暂存区删除**:

格式：git rm --cached 文件名

```shell
[root@ali_cloud git_data]$ git rm --cached file3  #这个命令只会删除你暂存区的文件，并没有删除源文件
rm 'file3'
[root@ali_cloud git_data]$ git status
# On branch master
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#	modified:   guess_number.py
#
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
#	file3
no changes added to commit (use "git add" and/or "git commit -a")
[root@ali_cloud git_data]# 

```

Git提交项目流程

```
echo "# Gear-of-fate" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:gfeide/Gear-of-fate.git
git push -u origin main
```

