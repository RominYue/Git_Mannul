##补充提交的信息
###目标
学习如何修改和补充已经存在的提交
##01 修改程序然后提交
**文件 hello.rb**

	# Default is World
	# Author: Jim Weirich
	name = ARGV.first || "World"

	puts "Hello, #{name}!"
**执行代码**

`$ git add hello.rb`
`$ git commit -m "Add an author commit"`
##02 需要添加e-mail
当你做完提交之后，你意识到每一个不错的提交应该有一个email的信息。更新程序加一个email。  
**文件 hello.rb**

	# Default is World
	# Author: Jim Weirich (jim@somewhere.com)
	name = ARGV.first || "World"
	
	puts "Hello, #{name}!"
##03 修改补充之前的提交
**执行代码**

`$ git add hello.rb`   
`$ git commit --amend -m "Add an author/email comment"`

**命令行输出**

	$ git add hello.rb
	$ git commit --amend -m "Add an author/email comment"
	[master eb30103] Add an author/email comment
	 1 files changed, 2 insertions(+), 1 deletions(-)
##04 观察历史
**执行代码**

`$ git hist`

**命令行输出**

	$ git hist
	* eb30103 2013-04-13 | Add an author/email comment (HEAD, master) [Jim Weirich]
	* 1f7ec5e 2013-04-13 | Added a comment (v1) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value (v1-beta) [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]

我们看到之前的"author"提交已经不见了，取而代之的是"author/email"提交记录。你可以通过回退到上一个版本然后再次提交达到相同的目的。

