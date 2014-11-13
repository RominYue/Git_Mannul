##撤销暂存区的修改（在提交之前）
###目标
学习如何撤销存储在暂存区的修改
##01 修改文件并提交至暂存区
**文件 hello.rb**

	# This is an unwanted but staged comment
	name = ARGV.first || "World"

	puts "Hello, #{name}!"
**执行代码**

`git add hello.rb`  
##02 检查状态
**执行代码**

`$ git status`

**命令行输出**

	$ git status
	# On branch master
	# Changes to be committed:
	#   (use "git reset HEAD <file>..." to unstage)
	#
	#	modified:   hello.rb
	#
status命令的输出告诉我们文件的修改已经存储在暂存区，随时准备提交。
##03 重置暂存区，恢复之前的状态
**执行代码**

`$ git reset HEAD hello.rb`

**命令行输出**

	$ git reset HEAD hello.rb
	Unstaged changes after reset:
	M	hello.rb
reset命令将在哪存取恢复到HEAD指向的内容。这将清楚我们之前在暂存区做的修改。

reset命令并不改变工作目录的内容。因此工作区中的hello.rb文件仍然有注释行。我们可以使用上一个lab的checkout命令来恢复它。
##04 切换到已提交的版本
**执行代码**

`$ git checkout hello.rb`  
`$ git status`

**命令行输出**

	$ git status
	# On branch master
	nothing to commit (working directory clean)
