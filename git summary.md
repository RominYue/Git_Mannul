##Git 总结
##01 安装git与初步配置
装完git之后，打开git bash 设置用户名和email  

	$ git config --global user.name "Your name"
	$ git config --global user.email "email@example.com"
##02 创建版本库
###首先创建一个工作目录
	$ mkdir test
	$ cd test
###然后初始化新仓库
	$ git init
##03 基本操作
###将工作区中的文件添加到版本库中
	$ git add example.txt
	$ git commit -m "example comment"
###检查文件/分支当前状态
	$ git status [filename]
###修改文件再次提交
	$ # modify operations
	$ git add example.txt
	$ git commit -m "modified"

###检查变化前和变化后的不同之处
	$ git diff [filename] (optional)
git diff 比较的是 index区域的对象和工作区的对象  
关于git diff显示格式的问题，参考[这里](http://www.ruanyifeng.com/blog/2012/08/how_to_read_diff.html)
###版本重置/回退
	$ git reset --hard <commit> (HEAD)
注意：该命令将暂存区和工作区都还原到commit版本。  
*补救措施*

	$ git reflog
	ea34578 HEAD@{0}: reset: moving to HEAD^
	3628164 HEAD@{1}: commit: append GPL
	ea34578 HEAD@{2}: commit: add distributed
找到对应版本的ID值，还原到该版本
###观察历史版本中的内容(不需要重置)
	$ git checkout <commit> # 先检出对应的commit
	$ cat example.txt
	$ git checkout master # 返回当前分支,让HEAD指针指回master分支
###撤销修改
	$ git checkout -- filename   
	# 用暂存区中的filename来替换工作区中的filename


	$ git reset <commit> <path/filename>  
	$ git reset HEAD filename  
	#用HEAD中版本覆盖暂存区中的文件，工作区不变
###修正提交信息
	$ git commit --amend -m "comment"
	#会覆盖之前顶点提交，只显示一条提交信息
##删除文件
	$ git rm filename
	# rm filename 只是删除了工作区中的文件，暂存区和版本库中还存在。
	# git rm 将暂存区中的文件也删除
	# git commit 之后版本库中的也会删除
##移动文件
	$ git mv a.file b.file/directory  
	$ # 然后执行 git commit
###文件的详细信息
	$ git cat-file -t <hash>
	#hash值所代表的type(tree,blob,commit,tag)

	$ git cat-file -p <hash>
	#列出hash值所代表文件类型的详细信息
##03 分支管理
###创建新分支
	$ git checkout -b <branchname>
等价于

	$ git branch <branchname>
	$ git checkout <branchname>
###查看分支
	$ git branch
###合并某分支到当前分支
	$ git merge <branchname>
	# 如果出现冲突，手动解决再提交
###删除分支
	$ git branch -d <branchname>
强行删除分支：

    $ git branch -D <branchname>
###切换分支时保存信息
	$ git stash  
	#保存index区域和工作区的内容，然后就可以切换分支了
查看stash储存的信息

	$ git stash list
	stash@{0}: WIP on dev: 6224937 add merge
取出stash存储的信息

	$ git stash pop  
	#恢复的同时把stash的内容删除

	$ git stash apply [<stash@{0}>]
	# 恢复，stash内容并不删除  
	$ git stash drop

##04 Git 远程操作
![](http://image.beekka.com/blog/2014/bg2014061202.jpg)
###git remote 命令
git remote 显示所有主机名称

	$ git remote
	origin

git remote -v 显示主机的网址

	$ git remote -v 
	origin  git@github.com:jquery/jquery.git (fetch)
	origin  git@github.com:jquery/jquery.git (push)

git remote show <主机名>，显示该主机的详细信息

	$ git remote show <主机名>

git remote add 用于添加远程主机，关联远程库

	$ git remote add <主机名> <网址>

git remote rm 用于删除远程主机，切断关联

	$ git remote rm <主机名>

git remote rename 用于远程主机的改名

	$ git remote rename <原主机名> <新主机名>

###git clone 命令
git clone 从远程主机克隆版本库

	$ git clone <版本库网址>

该命令会在本地主机生成一个目录，与远程主机的版本库同名。如果要指定不同的目录名，可以将目录名作为git clone命令的第二个参数。

	$ git clone <版本库网址> <本地目录名>

###git fetch 命令
远程版本库有了更新，需要取回本地

	$ git fetch <远程主机名>

默认情况下，git fetch取回所有分支（branch）的更新。如果只想取回特定分支的更新，可以指定分支名。  

	$ git fetch <远程主机名> <分支名>

git branch命令的-r选项，可以用来查看远程分支，-a选项查看所有分支。  

	$ git branch -r
	origin/master

	$ git branch -a
	* master
 	  remotes/origin/master
###git push 命令
git push命令用于将本地分支的更新，推送到远程主机。  

	$ git push <远程主机名> <本地分支名>:<远程分支名>
如果省略远程分支名，则表示将本地分支推送与之存在"追踪关系"的远程分支（通常两者同名），如果该远程分支不存在，则会被新建。比如：  

	$ git push origin master

如果省略本地分支名，则表示删除指定的远程分支，因为这等同于推送一个空的本地分支到远程分支。  

	$ git push origin :master
	# 等同于
	$ git push origin --delete master
如果远程主机的版本比本地版本更新，推送时Git会报错，要求先在本地做git pull合并差异，然后再推送到远程主机。
###git pull 命令
git pull命令的作用是，取回远程主机某个分支的更新，再与本地的指定分支合并  

	$ git pull <远程主机名> <远程分支名>:<本地分支名>

如果远程分支是与当前分支合并，则冒号后面的部分可以省略。比如：  

	$ git pull origin next:master  
等价于

	$ git pull origin next
等价于

	$ git fetch origin  
	$ git merge origin/next
关于git的远程操作，详细课参考[这里](http://www.ruanyifeng.com/blog/2014/06/git_remote.html)
##05 使用Github
###添加远程主机
	#SSH协议
	$ git remote add origin git@github.com:RominYue/example.git  

	#http协议
	$ git remote add origin https://github.com/RominYue/example.git
###提交版本库
	$ git push origin master