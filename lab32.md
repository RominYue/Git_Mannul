##重新设置greet分支
###目标
将greet分支还原到合并之前的状态
##01 还原greet分支
让我们回到greet分支在初次被合并前的状态。我们可以将分支还原到任意一次提交上。本质上它是将分支的指针移动到提交树的任意一个位置。
**执行代码**

`$ git checkout greet`  
`$ git hist`

**命令行输出**

	$ git checkout greet
	Already on 'greet'
	$ git hist
	*   25f0e8c 2013-04-13 | Merged master fixed conflict. (HEAD, greet) [Jim Weirich]
	|\  
	| * 05f32c0 2013-04-13 | Made interactive (master) [Jim Weirich]
	* |   844d1ed 2013-04-13 | Merge branch 'master' into greet [Jim Weirich]
	|\ \  
	| |/  
	| * b59a8c2 2013-04-13 | Added README [Jim Weirich]
	* | 28917a4 2013-04-13 | Updated Rakefile [Jim Weirich]
	* | 4dac415 2013-04-13 | Hello uses Greeter [Jim Weirich]
	* | 39347b3 2013-04-13 | Added greeter class [Jim Weirich]
	|/  
	* 96ee164 2013-04-13 | Added a Rakefile. [Jim Weirich]
	* 0f36766 2013-04-13 | Moved hello.rb to lib [Jim Weirich]
	* eb30103 2013-04-13 | Add an author/email comment [Jim Weirich]
	* 1f7ec5e 2013-04-13 | Added a comment (v1) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value (v1-beta) [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]

上述图形有一些难以让人阅读。但是我们看到"Update Rakefile"是在合并前的最后一次提交。  
**执行代码**

`$ git reset --hard <hash>`  

**命令行输出**

	$ git reset --hard 28917a4
	HEAD is now at 28917a4 Updated Rakefile
##02 检查分支
看看greet分支的历史记录，我们已经看不到合并的相关提交了。  
**执行代码**

`$ git hist --all`

**命令行输出**

	$ git hist --all
	* 05f32c0 2013-04-13 | Made interactive (master) [Jim Weirich]
	* b59a8c2 2013-04-13 | Added README [Jim Weirich]
	| * 28917a4 2013-04-13 | Updated Rakefile (HEAD, greet) [Jim Weirich]
	| * 4dac415 2013-04-13 | Hello uses Greeter [Jim Weirich]
	| * 39347b3 2013-04-13 | Added greeter class [Jim Weirich]
	|/  
	* 96ee164 2013-04-13 | Added a Rakefile. [Jim Weirich]
	* 0f36766 2013-04-13 | Moved hello.rb to lib [Jim Weirich]
	* eb30103 2013-04-13 | Add an author/email comment [Jim Weirich]
	* 1f7ec5e 2013-04-13 | Added a comment (v1) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value (v1-beta) [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]