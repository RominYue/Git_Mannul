##撤销本地修改(存储在暂存区之前)
###目标
学习如何在工作目录下撤销修改
##01 切换到分支的最新版本
确保在操作之前你处在最近一次提交的状态  

**执行代码**

`$ git checkout master`
##02 修改hello.rb
有时候你已经在本地工作目录下修改了文件，但是你想把它恢复到以前提交过的版本。此时我们将使用checkout命令。  

下面先改变hello.rb文件

**文件 hello.rb**

	# This is a bad comment.  We want to revert it.
	name = ARGV.first || "World"

	puts "Hello, #{name}!"
##03 检查状态
**执行代码**

`$ git status`  

**命令行输出**

	$ git status
	# On branch master
	# Changes not staged for commit:
	#   (use "git add <file>..." to update what will be committed)
	#   (use "git checkout -- <file>..." to discard changes in working directory)
	#
	#	modified:   hello.rb
	#
	no changes added to commit (use "git add" and/or "git commit -a")
我们发现hello.rb已经被修改，但是还没有存储在暂存区。
##04 本地工作目录下撤销修改
**执行代码**

`$ git checkout hello.rb`  
`$ git status`  
`$ cat hello.rb`

**命令行输出**

	$ git checkout hello.rb
	$ git status
	# On branch master
	nothing to commit (working directory clean)
	$ cat hello.rb
	# Default is "World"
	name = ARGV.first || "World"
	
	puts "Hello, #{name}!"
status命令的输出告诉我们当前目录中没有什么修改。“bad comment”再也不存在与文件hello.rb中了。
