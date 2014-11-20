##合并pulled changes
###目标
学习如何将变化合并到当前分支和工作目录
##01 Merge the fetch changes into local master
**执行代码**

`$ git merge origin/master`

**命令行输出**

	$ git merge origin/master
	Updating 2fae0b2..2e4c559
	Fast-forward
 	  README |    1 +
 	  1 files changed, 1 insertions(+), 0 deletions(-)
##02 检查README文件
**命令行代码**

`$ cat README`

**命令行输出**

	$ cat README
	This is the Hello World example from the git tutorial.
	(changed in original)
