##远程分支
###目标学习本地VS远程分支
让我们看看克隆库中有哪一些分支  
**执行代码**

`$ git branch` 

**命令行输出**

	$ git branch
	* master

只有master分支被显示出来。那么greet分支去哪里了？git branch命令默认显示的是本地分支。
##01 显示远程分支
**执行代码**

`$ git branch -a`  

**命令行输出**

	$ git branch -a
	* master
  	remotes/origin/HEAD -> origin/master
  	remotes/origin/greet
  	remotes/origin/master
git拥有原版本的所有提交，但是远程版本库的分支却不是本地分支。