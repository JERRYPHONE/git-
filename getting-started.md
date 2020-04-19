[mac Homebrew安装方法](https://www.jianshu.com/p/4e80b42823d5)

[mac git安装方法](https://www.jianshu.com/p/7edb6b838a2e)

在命令行输入想要创建库的路径然后敲git就可以开始写命令了

* git init：创建一个空的版本库，后面就可以往这个库里面放东西了

* git clone 链接：把该链接下仓库里的所有内容下载到指定的地址

不管是新建的空的库还是刚刚去把别人链接里扒拉下来的库，都会有一个master主分支，默认把内容存到master里；也可以新建别的分支，当有需要时再把那个分支合并到master分支里就可以了。分支可以随时增删，起到一个隔离的作用，灵活又安全。

* git branch 分支名称：创建分支
* git branch：列出分支

*  git checkout 分支名称：切换分支
* git checkout -b 分支名称：创建并切换到分支
* branch -d 分支名称：删除分支
* git merge 分支名称：把该分支合并到master里

回到master，当我们往本地目录添加了新的资源时，资源也仅仅是存在于本地的，和普通的文件夹没什么区别，而发挥git版本控制系统的作用，则需要把刚刚这个新增加资源这件事告诉git，让它来帮你管理。

* git add 文件：添加文件
* git add .：添加全部文件
* rm 文件：删除文件

这里的增减资源相当于把我做了什么告诉了git，但是还尚未保存，

* git commit -m "操作描述"：提交更新
* git commit -am"操作描述"：add+commit

* git commit --amend -m"操作描述"：修改当前commit操作描述，在日志里不新增版本
* git status：查看状态，在commit前后可以通过该命令来查看当前资源的add和commit状态

经过commit才算是让git帮你保存了一个版本的操作，假设经过几个版本的操作后，我怎么才能知道我都提交了哪些操作、某两个版本之间做了什么改变呢？

* git log：查看提交历史
* git diff 版本号1 版本号2：比较两个版本的修改

当然，如果你只是今天在继续编辑时，忘记相对于刚刚的添加/上一版本/某一版本自己做了什么修改，当前的状态还没commit，自然没有版本号可以用来对比，此时就可以用以下的命令来进行对比。

* git diff：比较新修改未add和已add的区别
* git diff HEAD：比较新修改未add和已commit的区别
* git diff 版本号：比较新修改未add和某版本的区别

以上的操作都是可以在无网状态下操作的，这也是git的优势所在，现在我要把保存好的东西分享出去就需要联网并提交了。

* git push origin master：更新到远程库去，origin是远程库，master提交到master分支
* git pull：获取远程库并与本地内容整合

*注意操作顺序是先commit再pull再push，避免造成覆盖。

