##Git 内部探秘：.git 目录
###目标
学习.git目录的文件结构
##01 .git 目录
**执行代码**

`$ ls -C .git`

**命令行输出**

	$ ls -C .git
	COMMIT_EDITMSG	ORIG_HEAD	hooks		logs		rr-cache
	HEAD		config		index		objects
	MERGE_RR	description	info		refs
##02 Objects目录
**执行代码**

`$ ls -C .git/objects`

**命令行输出**

	$ ls -C .git/objects
	09	1f	27	43	69	83	97	af	e4	info
	0f	22	28	58	6b	94	9c	b5	e7	pack
	11	24	32	59	78	96	a1	c4	eb
你将会看到一簇以两个字母或数字命名的目录。该目录的名字就是存储在git目录下的东西的sha1 hash值的前两位。

##03 深入探究Obejects目录
**执行代码**

`$ ls -C .git/objects/<dir>`  

**命令行输出**

	$ ls -C .git/objects/09
	6b74c56bfc6b40e754fc0725b8c70b2038b91e9fb6f9d3a104feb32fcac22354c4d0e8a182c1
我们现在进入其中一个目录。你将会看到以38个字母数字命名的文件。这就是那些存储git中物件的文件。这一些文件被压缩和编码，因此查看文件内容不会有多大用。
##04 Config 文件
**执行代码**

`$ cat .git/config`

**命令行输出**

	$ cat .git/config
	[core]
		repositoryformatversion = 0
		filemode = true
		bare = false
		logallrefupdates = true
		ignorecase = true
	[user]
		name = Jim Weirich
		email = jim (at) neo.com
上述的是依赖于特定工程的配置文件。在这儿罗列出的条目将会覆盖在home目录中.gitconfig文件中的条目，至少在此工程中是这样。
##05 分支和标签
**执行代码**

`$ ls .git/refs`  
`$ ls .git/refs/heads`  
`$ ls .git/refs/tags`  
`$ cat .git/refs/tags/v1`

**命令行输出**

	$ ls .git/refs
	heads
	tags
	$ ls .git/refs/heads
	master
	$ ls .git/refs/tags
	v1
	v1-beta
	$ cat .git/refs/tags/v1
	1f7ec5eaa8f37c2770dae3b984c55a1531fcc9e7
你应该已经认出了tag子目录下的文件是什么。每一个文件对应的恰是之前用git tag 命令创建的标签。它的内容就是该标签指向的提交的hash值。

heads目录同是如此。但它所显示的是分支而不是标签。在某一时刻我们只能有一个分支，所以你只能在此目录下看到master分支。
##06 HEAD 文件
**执行代码**

`$ cat .git/HEAD`

**命令行输出**

	$ cat .git/HEAD
	ref: refs/heads/master
HEAD文件包含了指向当前分支的一个引用。
