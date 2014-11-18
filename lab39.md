##什么是Origin？
###目标
学习如何命名远端版本库  
**执行代码**

`$ git remote`

**命令行输出**

	$ git remote
	origin
我们知道这个克隆的版本库了解一个叫做origin的远程版本库。  
**执行代码**

`$ git remote show origin` 

**命令行输出**

	$ git remote show origin
	* remote origin
  	Fetch URL: /Users/jim/working/git/git_immersion/auto/hello
  	Push  URL: /Users/jim/working/git/git_immersion/auto/hello
  	HEAD branch (remote HEAD is ambiguous, may be one of the following):
    	greet
    	master
  	Remote branches:
    	greet  tracked
现在我们发现这个远程库origin就是hello版本库。典型的远程库基本上都在远端的服务器上。但我们在这儿看到的，它也可以存在与本机上。