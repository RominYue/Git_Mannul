##版本回退
###目标
学习如何检查以前版本，以便将当前版本回退到该版本
##01 获得以前版本的hash值
**执行命令**

`$ git hist`

**命令行输出**

	$ git hist
	* 1f7ec5e 2013-04-13 | Added a comment (HEAD, master) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]
    
检查日志输出并且找到第一条提交的hash值。它应该是输出中的最后一行。在下面的命令中使用该hash值，然后观察hello.rb的内容。  
**执行代码**

`$git checkout <hash>`  
`cat hello.rb`

**命令行输出**

	$ git checkout 9416416
	Note: checking out '9416416'.

	You are in 'detached HEAD' state. You can look around, make experimental
	changes and commit them, and you can discard any commits you make in this
	state without impacting any branches by performing another checkout.

	If you want to create a new branch to retain commits you create, you may
	do so (now or later) by using -b with the checkout command again. Example:

  	git checkout -b new_branch_name

	HEAD is now at 9416416... First Commit
	$ cat hello.rb
	puts "Hello, World"
"detached HEAD" 这则消息说明HEAD现在指向的是一个提交而不是一个分支。只要你不切换到另一个分支上，在这种状态下的修改都会被记住。当你切换到一个新的分支或者是标签时，这一些分离的提交就会丢失（因为HEAD指针移动了）。如果在这种状态下你想保存提交，你需要创建一个新的分支来记这一些提交。  
##02 返回master分支最新的版本
**执行代码**  

`$ git checkout master`
`$ cat hello.rb`

**命令行输出**

	$ git checkout master
	Previous HEAD position was 9416416... First Commit
	Switched to branch 'master'
	$ cat hello.rb
	# Default is "World"
	name = ARGV.first || "World"

	puts "Hello, #{name}!"
