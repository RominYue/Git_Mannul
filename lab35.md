##合并到master分支上
###目标
之前我们是让master分支合并到greet分支上，现在我们让greet分支合并到master分支上。  
**执行代码**

`$ git checkout master`  
`$ git merge greet`  

**命令行输出**

	$ git checkout master
	Switched to branch 'master'
	$
	$ git merge greet
	Updating b59a8c2..2fae0b2
	Fast-forward
 	 Rakefile       |    2 +-
 	 lib/greeter.rb |    8 ++++++++
 	 lib/hello.rb   |    6 ++++--
 	 3 files changed, 13 insertions(+), 3 deletions(-)
 	 create mode 100644 lib/greeter.rb
##02 回顾日志
**执行代码**

`$ git hist`

**命令行输出**

	$ git hist
	* 2fae0b2 2013-04-13 | Updated Rakefile (HEAD, master, greet) [Jim Weirich]
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

