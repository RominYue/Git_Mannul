##提交修改
###目标
学习如何将修改提交到版本库
##01 提交修改
好的，关于暂存的部分已经讲的差不多了。下面就让我们提交已经暂的修改吧。

当你以前使用git commit命令提交hello.rb的早期版本至版本库时，你使用了-m的参数在命令行加了一行关于commit的注释。当然，commit命令可以允许你交互地为这个commit命令编辑注释。现在让我们尝试一下。

如果命令行中遗忘了-m的参数，git将会自动进入默认的编辑器中。编辑器将会从下列表中选择：  

- GIT_EDITOR 环境变量
- core.editor 环境设置
- VISUAL 环境变量
- EDITOR 环境变量

我将EDITOR环境变量设置为emacs。    
现在可以提交和检查状态了。  

**执行代码** 
 
`$ git commit`

**命令行输出**

	|
	# Please enter the commit message for your changes. Lines starting  
	# with '#' will be ignored, and an empty message aborts the commit. 
	# On branch master
	# Changes to be committed:  
	#   (use "git reset HEAD <file>..." to unstage)  
	#  
	#	modified:   hello.rb  
	#

在第一行，输入注释：“Using ARGV”，保存文件并退出编辑器。  

**命令行输出**

	git commit
	Waiting for Emacs...
	[master 569aa96] Using ARGV
 	1 files changed, 1 insertions(+), 1 deletions(-)

"Waiting for Emacs"这一行来自emacs的客户端。它将打开一个运行的emacs的编辑器，并等待文件被编辑完。输出的剩余部分才是标准的commit命令的输出语句。
##02 检查状态
**执行代码**

`$ git status`

**命令行输出**

	$ git status
	# On branch master
	nothing to commit (working directory clean)
