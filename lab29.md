##创建一个冲突
###目标
在master分支中创建一个导致冲突的修改
##01 切换到master分支，创建一个冲突
**执行代码**

`$ git checkout master`

**文件 lib/hello.rb**

	puts "What's your name"
	my_name = gets.strip

	puts "Hello, #{my_name}!"
**执行代码**

`$ git add lib/hello.rb`
`$ git commit -m "Made interactive"`

##02 观察所有分支
**执行代码**

`$ git hist --all`

**命令行输出**

	$ git hist --all
	*   844d1ed 2013-04-13 | Merge branch 'master' into greet (greet) [Jim Weirich]
	|\  
	* | 28917a4 2013-04-13 | Updated Rakefile [Jim Weirich]
	* | 4dac415 2013-04-13 | Hello uses Greeter [Jim Weirich]
	* | 39347b3 2013-04-13 | Added greeter class [Jim Weirich]
	| | * 05f32c0 2013-04-13 | Made interactive (HEAD, master) [Jim Weirich]
	| |/  
	| * b59a8c2 2013-04-13 | Added README [Jim Weirich]
	|/  
	* 96ee164 2013-04-13 | Added a Rakefile. [Jim Weirich]
	* 0f36766 2013-04-13 | Moved hello.rb to lib [Jim Weirich]
	* eb30103 2013-04-13 | Add an author/email comment [Jim Weirich]
	* 1f7ec5e 2013-04-13 | Added a comment (v1) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value (v1-beta) [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]

master分支的"Added README"已经合并到greet分支。但是master分支又新添了一个提交，它还没有被合并到greet分支。
