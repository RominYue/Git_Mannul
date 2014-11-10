##是修改，而不是文件
###目标
学习git用于修改而不是文件本身

大多数的版本控制系统是以保存文件的方式工作。添加一个文件到版本控制，然后系统将追踪该文件的变化。

Git文件的变化而非文件本身。当你告诉git要添加文件的时候，你不是告诉git要将文件添加到版本库，而是说git需要记录当前文件的信息状态，以便以后可以提交。

我们将尝试着去探索这种不同
##01 第一次修改：添加一个默认名
修改“Hello world”程序，当命令行不提供参数的时候，使之有一个默认值。  

**文件 hello.rb**
   
	name = ARGV.first || "World"
	
	puts "Hello, #{name}!"
##02 添加这种修改
**执行代码**

`$ git add hello.rb`
##03 第二次修改：添加一行注释
**文件 hello.rb**

	# Default is "World"
	name = ARGV.first || "World"

	puts "Hello, #{name}!"
##04 检查当前状态
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
	# Changes not staged for commit:
	#   (use "git add <file>..." to update what will be committed)
	#   (use "git checkout -- <file>..." to discard changes in working directory)
	#
	#	modified:   hello.rb
	#
注意hello.rb展现出来了两种状态。第一次修改储存在暂存区，随时可以提交。第二次修改并没有储存在暂存区。如果现在执行commit命令，在版本库中的hello.rb将没有那一行注释。  
现在我们尝试一下。
##05 提交修改
提交暂存区的修改  
**执行代码**

`$ git commit -m "Add a default value"`  
`$ git status`

**命令行输出**

	$ git commit -m "Added a default value"
	[master 582495a] Added a default value
	 1 files changed, 3 insertions(+), 1 deletions(-)
	$ git status
	# On branch master
	# Changes not staged for commit:
	#   (use "git add <file>..." to update what will be committed)
	#   (use "git checkout -- <file>..." to discard changes in working directory)
	#
	#	modified:   hello.rb
	#
	no changes added to commit (use "git add" and/or "git commit -a")
status命令告诉我们hello.rb有修改没有被记录到版本库中，也不在暂存区中。  
##06 添加第二次修改
**执行代码**

`$ git add .`  
`$ git status`

注意：这里我们用当前目录'.'来添加修改。这是一种非常简便快捷的方式来添加当前目录及子目录所有文件的修改。但是它添加了所有的修改，我们建议在执行 "add ." 命令之前，先检查当前状态，仅仅是确保你添加了正确的文件。

**命令行输出**

	$ git status
	# On branch master
	# Changes to be committed:
	#   (use "git reset HEAD <file>..." to unstage)
	#
	#	modified:   hello.rb
	# 
现在第二次修改已经存储在暂存区中，随时可以提交。
##07 提交第二次修改
**执行代码**

`$ git commit -m "Add a comment"`