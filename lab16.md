##撤销已提交的修改
###目标
学习如何撤销已提交至版本库的修改
##01 撤销提交
有时候你意识到你已经提交的修改有不对的地方，你想撤销该操作。有几种办法都可以解决这个问题，我们在这儿讨论的方法都是安全的。

要想撤销该操作，本质上我们是做一次新的提交覆盖之前的操作。
##02 修改文件并提交
**文件hello.rb**

	# This is an unwanted but committed change
	name = ARGV.first || "World"

	puts "Hello, #{name}!"
**执行代码**

`$ git add hello.rb`  
`$ git commit -m "Oops,we did not want to commit"`
##03 创建一个新的提交
为了撤销一条已经提交的修改，我们需要新建一个提交来消除已经提交的修改的影响。  
**执行代码**

`$ git revert HEAD`

你将会进入编辑器，编辑此次提交的注释。

**命令行输出**

	$ git revert HEAD --no-edit
	[master a10293f] Revert "Oops, we didn't want this commit"
 	1 files changed, 1 insertions(+), 1 deletions(-)
因为我们还原的是最后一次提交的版本，所以这里我们用HEAD作为参数。我们可以还原以前提交的任意版本通过查询他们的hash值。
##04 检查日志
**执行代码**

`$ git hist` 

**命令行输出**

	$ git hist
	* a10293f 2013-04-13 | Revert "Oops, we didn't want this commit" (HEAD, master) [Jim Weirich]
	* 838742c 2013-04-13 | Oops, we didn't want this commit [Jim Weirich]
	* 1f7ec5e 2013-04-13 | Added a comment (v1) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value (v1-beta) [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]
这个命令可以还原任意提交的版本。同时他也是非常安全的，及时分支已经在远程库上分享了。

