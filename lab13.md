##标记版本
###目标
学习如何给提交打标签  
我们把现在的这个hello程序叫做版本v1
##01 标记 标签1
**执行代码**

`$ git tag v1`

那么现在你可以把当前工程的版本叫做v1了。
##02 标记 以前的版本
我们打算将v1的前一个版本标记为v1-beta。首先我们要切换到之前的版本。我们不需要使用提交的hash值，我们可以使用"^"符号来表示"v1的父亲结点"。  
**执行代码**

`$ git checkout v1^`  
`cat hello.rb`

**命令行输出**

$ git checkout v1^
	Note: checking out 'v1^'.

	You are in 'detached HEAD' state. You can look around, make experimental
	changes and commit them, and you can discard any commits you make in this
	state without impacting any branches by performing another checkout.

	If you want to create a new branch to retain commits you create, you may
	do so (now or later) by using -b with the checkout command again. Example:

  	   git checkout -b new_branch_name

	HEAD is now at 582495a... Added a default value
	$ cat hello.rb
	name = ARGV.first || "World"

	puts "Hello, #{name}!"
你瞧，现在的版本恰好就是我们添加注释之前带有默认值的提交。现在我们把它标记为v1-beta版本.  
**执行代码**

`$ git tag v1-beta`

##03 通过标签来切换状态
现在我们尝试一下进行两个版本的切换。  
**执行代码**

`$ git checkout v1`  
`$ git checkout v1-beta`

**命令行输出**

	$ git checkout v1
	Previous HEAD position was 582495a... Added a default value
	HEAD is now at 1f7ec5e... Added a comment
	$ git checkout v1-beta
	Previous HEAD position was 1f7ec5e... Added a comment
	HEAD is now at 582495a... Added a default value
##04 通过使用tag命令观察已经标记的标签
**执行代码**

`$ git tag`

**命令行输出**

	$ git tag
	v1
	v1-beta
##05 在日志中观察标签
**执行代码**

`$ git hist master --all`

**命令行输出**

	$ git hist master --all
	* 1f7ec5e 2013-04-13 | Added a comment (v1, master) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value (HEAD, v1-beta) [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]
你可以在日志输出中看到v1和v1-beta，还有分支名master。同时HEAD指明当前查看的提交。