##合并分支
###目标
学习如何合并分支从而将修改合并到一个分支中
##01 合并分支
**执行代码**

`$ git checkout greet`  
`$ git merge master`  
`$ git hist --all`

**命令行输出**

	$ git checkout greet
	Switched to branch 'greet'
	$ git merge master
	Merge made by recursive.
 	 README |    1 +
 	 1 files changed, 1 insertions(+), 0 deletions(-)
 	 create mode 100644 README
	$ git hist --all
	*   844d1ed 2013-04-13 | Merge branch 'master' into greet (HEAD, greet) [Jim Weirich]
	|\  
	| * b59a8c2 2013-04-13 | Added README (master) [Jim Weirich]
	* | 28917a4 2013-04-13 | Updated Rakefile [Jim Weirich]
	* | 4dac415 2013-04-13 | Hello uses Greeter [Jim Weirich]
	* | 39347b3 2013-04-13 | Added greeter class [Jim Weirich]
	|/  
	* 96ee164 2013-04-13 | Added a Rakefile. [Jim Weirich]
	* 0f36766 2013-04-13 | Moved hello.rb to lib [Jim Weirich]
	* eb30103 2013-04-13 | Add an author/email comment [Jim Weirich]
	* 1f7ec5e 2013-04-13 | Added a comment (v1) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value (v1-beta) [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]

通过将maser分支合并到当前分支，你可以在master分支内做任意的修改，然后同步到greet分支中。

但是，merge操作显示出来的图形过于丑陋，下一章我们将介绍rebase来处理这个问题。
