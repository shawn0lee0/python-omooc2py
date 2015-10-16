#常用命令 
最常用 ： `git command --help `

> [Git命令参考](http://blog.chinaunix.net/uid-25806493-id-3328322.html)
> 
> [GIT 下载](http://git-scm.com/downloads)

## 1. 创建

**需要进入目标目录进行操作** 

+ 创建新仓库：`git init`
+ 创建一个本地仓库的克隆版本：`git clone /path/to/repository`
+ 克隆远端服务器的仓库：`git clone username@host:/path/to/repository`

## 2. 查询
   
`git status`

+ staged:已在index，等待被commit.
+ unstaged:文件做了改动，但还不能被commit.
+ untracked:Git还没有开始跟踪，需要先add.
+ deleted:文件已被删除，等待remove.

Staging Area:commit前把文件们收集到一起，以便打包commit。

 

## 3.添加add
+ 添加到暂存区（让Git开始跟踪更改，也就是从untracked变为tracked）：`git add <filename> 或 git add *`
+ 添加全部文件：`git add -A`， -A 表示包含删除的文件。
+ `git reset: git reset <filename> `从staging area移除文件。


## 4.commit 提交

"commit" 可以理解为一次快照，帮助我们把所有改动以timeline的方式组织起来。

+ 提交改动(到head，但还没到远程服务器)：`git commit -m `"代码提交信息"`git commit -m `  'Add all files' 
+ 把所有当前目录下的文件加入暂存区域再运行commit：`git commit -a`
+ 提交到远程仓库：`git push origin master `（可以把 master 换成你想要推送的任何分支）。
	
	如果还没有克隆现有仓库，并想将仓库连接到某个远程服务器：`git remote add origin <server>`。
   
## 5.Push推送（上传）

将文件推送到远程仓库中：`git push -u origin master`。远程仓库默认叫origin 。-u 告诉Git记住参数，下次可以直接使用push。

参考：`git push --help`

   
## 6.Pull提取（拉）
更新本地仓库与服务器端同步：`git pull origin master`

## 7.checkout（切换）
checkout命令用于从历史提交（或者暂存区域）中拷贝文件到工作目录，也可用于切换分支

+ 切换分支： `git checkout <branch>`
+ 新建并切换到分支：`git checkout -b new_branch` 等同于：`git branch new_branch` + `git checkout new_branch`
+ 把文件从暂存区域复制到工作目录，用来丢弃本地修改：`git checkout --<files>`
+ 回滚到复制最后一次提交:`git checkout HEAD -- <files>`



## 8.diff（比对）

git diff

> git-diff - Show changes between commits, commit and working tree, etc


> `git diff [options] [<commit>] [--] [<path>…​]`
> `git diff [options] --cached [<commit>] [--] [<path>…​]`
> `git diff [options] <commit> <commit> [--] [<path>…​]`
> `git diff [options] <blob> <blob>`
> `git diff [options] [--no-index] [--] <path> <path>`




## 9.reset（撤销）

+ 从index中撤销所有文件：`git reset`
+ 从index中撤销最后一次add的文件：`git reset --<flies>`
+ 恢复之前版本：`git reset --hard`
+ 回滚到最近一次：`git checkout -- <target>`


## 10.merge（合并其他分支到当前分支）
`git merge`

> git-merge - Join two or more development histories together

> `git merge [-n] [--stat] [--no-commit] [--squash] [--[no-]edit]`
> `[-s <strategy>] [-X <strategy-option>] [-S[<key-id>]]`
> `[--[no-]rerere-autoupdate] [-m <msg>] [<commit>…​]`
> `git merge <msg> HEAD <commit>…`​
> `git merge --abort`


## 11.remove & clean

+ 从硬盘和index移除文件：`git rm`
+ 删除分支`git branch -d <branch name>`

> git-rm - Remove files from the working tree and from the index






### 参考：

 [分布式版本控制系统-Git详解](http://vdisk.weibo.com/s/aGfNhFvjWLs1i)