##分支导航
###目标
学习如何在版本库中切换分支。  
你现在已经拥有了两个分支。

**执行代码** 

`$ git hist --all`

**命令行输出**

	$ git hist --all
	* 28917a4 2013-04-13 | Updated Rakefile (HEAD, greet) [Jim Weirich]
	* 4dac415 2013-04-13 | Hello uses Greeter [Jim Weirich]
	* 39347b3 2013-04-13 | Added greeter class [Jim Weirich]
	* 96ee164 2013-04-13 | Added a Rakefile. (master) [Jim Weirich]
	* 0f36766 2013-04-13 | Moved hello.rb to lib [Jim Weirich]
	* eb30103 2013-04-13 | Add an author/email comment [Jim Weirich]
	* 1f7ec5e 2013-04-13 | Added a comment (v1) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value (v1-beta) [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]

##01 切换至master分支
**执行代码**

`$ git checkout master`  
`$ cat lib/hello.rb`  

**命令行输出**

	$ git checkout master
	Switched to branch 'master'
	$ cat lib/hello.rb
	# Default is World
	# Author: Jim Weirich (jim@somewhere.com)
	name = ARGV.first || "World"

	puts "Hello, #{name}!"
你现在在master分支。你可以区分出来因为此处的hello.rb文件没有调用greeter类。
##02 切换至greet分支
**执行代码**

`$ git checkout greet`  
`$ cat lib/hello.rb`  

**命令行输出**

	$ git checkout greet
	Switched to branch 'greet'
	$ cat lib/hello.rb
	require 'greeter'

	# Default is World
	name = ARGV.first || "World"

	greeter = Greeter.new(name)
	puts greeter.greet
