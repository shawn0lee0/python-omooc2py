#1. [Gitbook与Github互推配置](https://zoejane.gitbooks.io/zoe-py-tutorial/content/gitbook-github.html)

#2. [开智·官方资料](https://github.com/OpenMindClub/OMOOC.py/wiki/gitbook_double_push)

大家将教程写在Github（全世界最cool的开源社区），如果能同时生成gitbook就好了，那么如何做到Github库和gitbook保持版本同步呢？gitbook有一个Github integration功能，理论上能实现我们的需求。嗯，只是理论上。亲测这个功能还没有完善。

不怕，我们可以用git自带的，同时push到两个库的功能。请按照下面的办法操作：

登录进去gitbook，在右上角有一个加号(Create New Book)，点击这个加号后，会出现新建图书页面，填好心仪的标题并确认。

这时候进入了新书的初始化界面，上面有两个选项，一个是现在开始写，一个是联动Github，都不要点，看到下面的…or push an existing repository from the command line了吗，这个标题下面第一行有一个https开头、.git结尾，例如：https://git.gitbook.com/<你的ID>/<仓库名>.git的网址，把这个网址复制下来。

首先，将之前建立的Github的库克隆到本地（具体方法在第一段）。
进入库文件夹。

 cd 本地库的名字 （因为是从github上拽下来的, 所以就是github上库的名字哦。）

输入`vi ./.git/config`

进入vi的编辑界面后，按i，进入编辑模式，在[remote "origin"]下一行，输入：`url = 刚才复制的网址`.

完事，config的效果应该是这样的：

> [remote "origin"]	
> 
> url = git@github.com:<id>/<name>.git
> 
> url = https://git.gitbook.com/<id>/<name>.git
> 
> fetch = +refs/heads/*:refs/remotes/origin/* 

**补充：**

在命令模式下键入：
`ZZ`
或者：
`:wq`
保存修改并且退出 `vi` 

如果只想保存文件，则键入：
`:w`
> [vi环境操作命令](http://blog.chinaunix.net/uid-20671208-id-3721795.html)


记得第一次使用 git push -u origin master哦 
> 这里一个小小提示：要确保你的 GitBook 的邮箱已验证哦。在 Git Book 右上角的 Account Settings 里。  

之后的push就不用加 -u 这个参数了，但是每次都会同时push到Github和gitbook，要注意不要从gitbook pull回来文件，gitbook只作为一个push过去的容器，不要再单独操作gitbook的库了。