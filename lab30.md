##解决冲突
###目标
学习如何在合并的过程中处理冲突
##01 合并master到greet分支
**执行代码**

`$ git checkout greet`  
`$ git merge master`

**命令行输出**

	$ git checkout greet
	Switched to branch 'greet'
	$ git merge master
	Auto-merging lib/hello.rb
	CONFLICT (content): Merge conflict in lib/hello.rb
	Automatic merge failed; fix conflicts and then commit the result.
如果你打开lib/hello.rb,你将会看到：  
**文件 lib/hello.rb**

	<<<<<<< HEAD
	require 'greeter'

	# Default is World
	name = ARGV.first || "World"

	greeter = Greeter.new(name)
	puts greeter.greet
	=======
	# Default is World

	puts "What's your name"
	my_name = gets.strip

	puts "Hello, #{my_name}!"
	>>>>>>> master
	
首先的版本是greet分支上的版本，第二个版本是master分支上的版本。

##02 修正冲突
你需要手动解决冲突。修改hello.rb文件。  
**文件 lib/hello.rb**

	require 'greeter'
	
	puts "What's your name"
	my_name = gets.strip

	greeter = Greeter.new(my_name)
	puts greeter.greet
##03 提交解决后的冲突
**执行代码**

`$ git add lib/hello.rb`  
`$ git commit -m "Merged master fixed conflict."`

**命令行输出**

	$ git add lib/hello.rb
	$ git commit -m "Merged master fixed conflict."
	Recorded resolution for 'lib/hello.rb'.
	[greet 25f0e8c] Merged master fixed conflict.
