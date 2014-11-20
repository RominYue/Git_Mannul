##获取变化
###目标
学会如何从远程库导入变化  
**执行代码**

`$ cd ../cloned_hello`  
`$ git fetch`  
`$ git hist --all`

**命令行输出**

	$ git fetch
	From /Users/jim/working/git/git_immersion/auto/hello
   		2fae0b2..2e4c559  master     -> origin/master
	$ git hist --all
	* 2e4c559 2013-04-13 | Changed README in original repo (origin/master, origin/HEAD) [Jim Weirich]
	* 2fae0b2 2013-04-13 | Updated Rakefile (HEAD, origin/greet, master) [Jim Weirich]
	* 1c23048 2013-04-13 | Hello uses Greeter [Jim Weirich]
	* 62d7ce0 2013-04-13 | Added greeter class [Jim Weirich]
	* b59a8c2 2013-04-13 | Added README [Jim Weirich]
	* 96ee164 2013-04-13 | Added a Rakefile. [Jim Weirich]
	* 0f36766 2013-04-13 | Moved hello.rb to lib [Jim Weirich]
	* eb30103 2013-04-13 | Add an author/email comment [Jim Weirich]
	* 1f7ec5e 2013-04-13 | Added a comment (v1) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value (v1-beta) [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]

现在版本库已经拥有了原版本库的所有提交信息。
##01 检查README文件
**执行代码**

`cat README`  

**命令行输出**

	$ cat README
	This is the Hello World example from the git tutorial.
