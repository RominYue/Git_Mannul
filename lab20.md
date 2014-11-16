##移动文件
###目标
学习如何在版本库中移动文件
##01 将hello.rb文件移动到lib目录下
我们现在将会组织版本库的结构。  

**执行代码**

`$ mkdir lib`  
`$ git mv hello.rb lib`  
`$ git status`

**命令行输出**

	$ mkdir lib
	$ git mv hello.rb lib
	$ git status
	# On branch master
	# Changes to be committed:
	#   (use "git reset HEAD <file>..." to unstage)
	#
	#	renamed:    hello.rb -> lib/hello.rb
	#
通过使用git来移动文件，其实告诉了git两件事情：  
文件hello.rb已经被删除  
文件 lib/hello.rb 被创建  
这两项都会立即存储在暂存区中，随时都可以被提交。
##02 移动文件的另一种方法
**执行代码**

`$ mkdir lib`  
`$ mv hello.rb lib`  
`$ git add lib/hello.rb`  
`$ git rm hello.rb`  
##03 提交新的目录
**执行代码**

`$ git commit -m "Moved hello.rb to lib"` 
