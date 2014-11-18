##还原master分支
###目标
还原master分支到产生冲突之前
##01 还原master分支
当我们在master分支添加interactive mode的时候，它与greet分支的内容产生了冲突。现在让我们来还原master分支。  
**执行代码**

`$ git checkout master`  
`$ git hist`

**命令行输出**

	$ git hist
	* 05f32c0 2013-04-13 | Made interactive (HEAD, master) [Jim Weirich]
	* b59a8c2 2013-04-13 | Added README [Jim Weirich]
	* 96ee164 2013-04-13 | Added a Rakefile. [Jim Weirich]
	* 0f36766 2013-04-13 | Moved hello.rb to lib [Jim Weirich]
	* eb30103 2013-04-13 | Add an author/email comment [Jim Weirich]
	* 1f7ec5e 2013-04-13 | Added a comment (v1) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value (v1-beta) [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]

"Added README"提交刚好处于我们想要还原的位置。  
**执行代码**

`$ git reset --hard <hash>`
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

