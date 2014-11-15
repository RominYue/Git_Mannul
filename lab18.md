##清除oops标签
###目标
清除之前的oops标签
##01 清除标签oops
oops标签已经完成了它的作用。让我们清除它并让与之相关的提交也被回收。  
**执行代码**

`$ git tag -d oops`  
`$ git hist --all`

**命令行输出**

	$ git tag -d oops
	Deleted tag 'oops' (was a10293f)
	$ git hist --all
	* 1f7ec5e 2013-04-13 | Added a comment (HEAD, v1, master) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value (v1-beta) [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]

