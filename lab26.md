##修改master分支
###目标
学习如何应对众多分支上的诸多修改  
当你在修改greet分支的时候，有人想要更新master分支。他决定添加一个Readme文件。  
##01 切换到master分支
**执行代码**

`$ git checkout master`  

##02 创建README文件
**文件 README**

	This is the Hello World example from the git tutorial.
##03 向master分支上提交README文件
**执行代码**

`$ git add README`  
`$ git commit -m "Added README"`  

