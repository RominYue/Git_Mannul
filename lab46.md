##Bare 版本库
###目标
学习如何创建一个bare版本库
##01 创建一个bare版本库
**执行代码**

`$ cd ..`  
`$ git clone --bare hello hello.git`  
`$ ls hello.git`

**命令行输出**

	$ git clone --bare hello hello.git
	Cloning into bare repository hello.git...
	done.
	$ ls hello.git
	HEAD
	config
	description
	hooks
	info
	objects
	packed-refs
	refs
版本库叫法的传统是带有.git后缀都叫做bare版本库。