##观察克隆版本库
###目标
学习远端版本库的分支
##01 观察克隆的版本库
**执行代码**

`$ cd cloned_hello`  
`$ ls`

**命令行输出**

	$ cd cloned_hello
	$ ls
	README
	Rakefile
	lib
##02 观察版本库的历史记录
**执行代码**

`$ git hist --all`

**命令行输出**

	$ git hist --all
	* 2fae0b2 2013-04-13 | Updated Rakefile (HEAD, origin/master, origin/greet, origin/HEAD, master) [Jim Weirich]
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