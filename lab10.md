##历史记录
###目标
学习如何观察操作的历史记录

git log 命令的用处：得到一些列之前做的修改记录  

**执行代码**

`$ git log`

**命令行输出**

	$ git log
	commit 1f7ec5eaa8f37c2770dae3b984c55a1531fcc9e7
	Author: Jim Weirich <jim (at) neo.com>
	Date:   Sat Apr 13 15:20:42 2013 -0400

    	Added a comment

	commit 582495ae59ca91bca156a3372a72f88f6261698b
	Author: Jim Weirich <jim (at) neo.com>
	Date:   Sat Apr 13 15:20:42 2013 -0400

   		Added a default value

	commit 323e28d99a07d404c04f27eb6e415d4b8ab1d615
	Author: Jim Weirich <jim (at) neo.com>
	Date:   Sat Apr 13 15:20:42 2013 -0400

    	Using ARGV

	commit 94164160adf8faa3119b409fcfcd13d0a0eb8020
	Author: Jim Weirich <jim (at) neo.com>
	Date:   Sat Apr 13 15:20:42 2013 -0400

    	First Commit
##01 一行的方式显示历史记录
**执行代码**

`$ git log --pretty=oneline`

**命令行输出**

	$ git log --pretty=oneline
	1f7ec5eaa8f37c2770dae3b984c55a1531fcc9e7 Added a comment
	582495ae59ca91bca156a3372a72f88f6261698b Added a default value
	323e28d99a07d404c04f27eb6e415d4b8ab1d615 Using ARGV
	94164160adf8faa3119b409fcfcd13d0a0eb8020 First Commit
##02 控制输出条目
我们可以自主选择在日志中显示哪一些条目。  
大家可以尝试下列选择：

- `$ git log --pretty=oneline --max-count=2`
- `$ git log --pretty=oneline --since='5 minutes ago'`
- `$ git log --pretty=oneline --until='5 minutes ago'`
- `$ git log --pretty=oneline --author=<your name>`
- `$ git log --pretty=oneline --all`

##03 让输出变得美妙
下面是我自己看历史记录时用的代码。可以添加 add --author=jim的方式来查看我自己做的修改。  
**执行代码**

`$ git log --pretty=format:'%h %cd %s %(an)' --since='7 days ago'`

##04 终极显示
**执行代码**

`$ git log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short`

**命令行输出**

	$ git log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short
	* 1f7ec5e 2013-04-13 | Added a comment (HEAD, master) [Jim Weirich]
	* 582495a 2013-04-13 | Added a default value [Jim Weirich]
	* 323e28d 2013-04-13 | Using ARGV [Jim Weirich]
	* 9416416 2013-04-13 | First Commit [Jim Weirich]
让我们更加深入地来看待输出形式。  

- --pretty="..." 定义了输出形式
- %h  是该提交hash值的缩写
- %d  是该提交的一些装饰用语(比如master分支等)
- %ad 表示作者提交的日期
- %s  表示提交时候的注释
- %an 表示作者姓名
- --graph 告诉git以ASCLL字符的形式画出提交树
- --date=short 以整洁简短的形式输出日期

