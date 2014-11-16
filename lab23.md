##探究.git目录，工作目录与git object
###目标
探寻object store的组织结构  
学习如何使用sha1 hash值来发现版本库中的内容  
##01 找寻最后的提交
**执行代码**

`$ git hsit --max-count=1`

**命令行输出**

	$ git hist --max-count=1
	* 96ee164 2013-04-13 | Added a Rakefile. (HEAD, master) [Jim Weirich]

##02 Dumping the last commit
使用上述列出的sha1 hash值。  
**执行代码**

`$ git cat-file -t <hash>`  
`$ git cat-file -p <hash>`

**命令行输出**

	$ git cat-file -t 96ee164
	commit
	$ git cat-file -p 96ee164
	tree 096b74c56bfc6b40e754fc0725b8c70b2038b91e
	parent 0f36766e05bc55d765ec8afe288430edc69fceea
	author Jim Weirich <jim (at) neo.com> 1365880844 -0400
	committer Jim Weirich <jim (at) neo.com> 1365880844 -0400

	Added a Rakefile.
##03 探究该次提交的文件目录树
我们可以输出目录树依据提交中的依赖关系。
**执行代码**

`$ git cat-file -p <treehash>`  

**命令行输出**

	$ git cat-file -p 096b74c
	100644 blob 28e0e9d6ea7e25f35ec64a43f569b550e8386f90	Rakefile
	040000 tree e46f374f5b36c6f02fb3e9e922b79044f754d795	lib
##04 输出lib目录
**执行代码**

`$ git cat-file -p <libhash>`  

**命令行输出**

	$ git cat-file -p e46f374
	100644 blob c45f26b6fdc7db6ba779fc4c385d9d24fc12cf72	hello.rb
##05 输出hello.rb 文件
**执行代码**

`$ git cat-file -p <rbhash>`  

**命令行输出**

	$ git cat-file -p c45f26b
	# Default is World
	# Author: Jim Weirich (jim@somewhere.com)
	name = ARGV.first || "World"

	puts "Hello, #{name}!"
我们从版本库中输出了tree object 和 commit object ，还有 blob object等。