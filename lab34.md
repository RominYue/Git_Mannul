##Rebasing
###目标
使用rebase命令而不是merge命令

这一次我们使用rebase命令而不是merge命令来合并分支。  
**执行代码**

`$ git checkout greet`  
`$ git rebase master`  
`$ git hist`

**命令行输出**

	$ go greet
	Switched to branch 'greet'
	$
	$ git rebase master
	First, rewinding head to replay your work on top of it...
	Applying: added Greeter class
	Applying: hello uses Greeter
	Applying: updated Rakefile
	$
	$ git hist
	* 2fae0b2 2013-04-13 | Updated Rakefile (HEAD, greet) [Jim Weirich]
	* 1c23048 2013-04-13 | Hello uses Greeter [Jim Weirich]
	* 62d7ce0 2013-04-13 | Added greeter class [Jim Weirich]
	* b59a8c2 2013-04-13 | Added README (master) [Jim Weirich]
	* 96ee164 2013-04-13 | Added a Rakefile. [Jim Weirich]
	* 0f36766 2013-04-13 | Moved hello.rb to lib [Jim Weirich]
	* eb30103 2013-04-13 | Add an author/email comment [Jim Weirich]
	* 1f7ec5e 2013-04-13 | Added a comment (v1) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value (v1-beta) [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]

##01 Merge VS Rebase
