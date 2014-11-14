##从一个分支里面清除提交
###目标
学习如何从一个分支中清除最近的提交

前一章节的revert命令是一个非常有用的命令，可以让我们撤销版本库中的任意提交。但是，缺点就是之前的提交和“撤销”操作的提交都会显示在git的历史记录中（使用git hist 可以看到）

通常情况下我们做一次提交然后马上发现它有一个错误。应该有一个“拿回”的命令来阻止这一次提交，就好像它没有发生过一样。同时这个“拿回”的命令也能阻止提交在git的历史记录中显示，就好像它不存在似的。
##01 reset 命令
我们已经见过reset命令并且已经使用它让暂存区中的状态和版本库中的某次提交的状态相一致。当给定一个commit的参数的时候（比如一个hash值，一个分支名，一个标签）：  

- 重写当前分支使之与特定的提交相一致
- 选择性的让暂存区的状态与某次提交的状态一致
- 选择性的让当前工作区的状态与某次提交的状态一致

##02 检查我们的历史记录
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

我们看到在当前分支中有"Oops..."和“Revert Oops..”两条提交。让我用reset命令来清除他们俩。
##03 首先，标记这个分支
**执行代码**

`% git tag oops`
##04 重置到Oops之前的状态
让我们看看输出的历史记录，标记为v1的提交刚好在Oops提交之前。我们将重置到该状态。因为分支已经被标记，我们可以在reset命令中使用该标签。  
**执行代码**

`$ git reset --hard v1`
`$ git hist`

**命令行输出**

	$ git reset --hard v1
	HEAD is now at 1f7ec5e Added a comment
	$ git hist
	* 1f7ec5e 2013-04-13 | Added a comment (HEAD, v1, master) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value (v1-beta) [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]
现在我们的master分支已经指向标记为v1的提交处。Oops提交和revert Oops提交已经不显示在日志中。--hard参数表明工作目录需要更新至与版本库相一致的状态。
##05 什么都没有丢失
那么"Oops..."和"Revert Oops"提交去哪里了？事实证明他们仍然在历史记录中。记得在一开始的时候我们将“Reverting Oops”提交标记成了“Oops”。  
**执行代码**

`$ git hist --all`

**命令行输出**

	$ git hist --all
	* a10293f 2013-04-13 | Revert "Oops, we didn't want this commit" (oops) [Jim Weirich]
	* 838742c 2013-04-13 | Oops, we didn't want this commit [Jim Weirich]
	* 1f7ec5e 2013-04-13 | Added a comment (HEAD, v1, master) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value (v1-beta) [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]

他们只是不会出现在master分支的历史记录中。即使我们不标记它们，它们依然存在于版本库中。但是我们将无法引用它们除非使用他们的hash值。这一些提交将会一直存在于版本库中直到启用垃圾回收机制。
##06 reset的危险之处
在本地分支上的reset操作总体来说很安全。任何发生的意外都可以再做一次reset操作既可以恢复之前的状态。

但是如果分支已在远程库上共享，reset操作可能会让其他使用者感到困惑。