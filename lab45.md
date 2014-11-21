##添加一个追踪分支
###目标
学习如何添加一个本地分支来追踪远程分支

含有rmotes/master的分支是来自于原版本库中的。注意到你已经不能使用greet分支了，虽然在原版本库中有这样的一个分支。
##01 添加一个本地分支追踪远程分支
**执行代码**

`$ git branch --track greet origin/master`  
`$ git branch -a`  
`$ git hist --max-count=2`

**命令行输出**

	$ git branch --track greet origin/greet
	Branch greet set up to track remote branch greet from origin.
	$ git branch -a
	  greet
	* master
	  remotes/origin/HEAD -> origin/master
	  remotes/origin/greet
	  remotes/origin/master
	$ git hist --max-count=2
	* 2e4c559 2013-04-13 | Changed README in original repo (HEAD, origin/master, origin/HEAD, master) [Jim Weirich]
	* 2fae0b2 2013-04-13 | Updated Rakefile (origin/greet, greet) [Jim Weirich]

