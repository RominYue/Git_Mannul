##递交一个修改
###目标
学习如何将修改提交至远程库

由于bare版本库经常共享与服务器上，他很难进入到版本库中提交修改。

修改README文件，然后提交  
**README 文件**

	This is the Hello World example from the git tutorial.
	(Changed in the original and pushed to shared)

**执行代码**

`$ git checkout master`  
`$ git add README`  
`$ git commit -m "Added shared comment to readme"`  

**执行代码**

`$ git push shared master`  

**命令行输出**

	$ git push shared master
	To ../hello.git
   	  2e4c559..3923dd5  master -> master
