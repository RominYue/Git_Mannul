##观察互相分离的分支
###目标
学习如何在版本库中观察分离的分支
##01 观察当前分支
现在版本库中有两个分支。  
**执行代码**

`$ git hist --all`

**命令行输出**

	$ git hist --all
	* b59a8c2 2013-04-13 | Added README (HEAD, master) [Jim Weirich]
	| * 28917a4 2013-04-13 | Updated Rakefile (greet) [Jim Weirich]
	| * 4dac415 2013-04-13 | Hello uses Greeter [Jim Weirich]
	| * 39347b3 2013-04-13 | Added greeter class [Jim Weirich]
	|/  
	* 96ee164 2013-04-13 | Added a Rakefile. [Jim Weirich]
	* 0f36766 2013-04-13 | Moved hello.rb to lib [Jim Weirich]
	* eb30103 2013-04-13 | Add an author/email comment [Jim Weirich]
	* 1f7ec5e 2013-04-13 | Added a comment (v1) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value (v1-beta) [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]

这是我们第一次在输出历史记录的时候使用了--graph参数。添加--graph参数可以在日志中以ASCLL字符的形式描绘提交树。我们可以同时看到两个分支，并且知道HEAD指向的是当前master分支。两个分支的共同祖先是“Add a Rakefile”提交。

--all参数可以显示所有的分支，默认的则只显示当前分支。

