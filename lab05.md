##做一些改变
###目标
学习如何监视工作目录的状态变化  
##01 改变“hello world” 程序文件
现在是时候改变一下hello程序文件了。现在我们要求程序本身要从命令行获取一个参数。将文件改为：   

`puts "Hello, #{ARGV.first}!"`  

##02 检查状态
现在检查一下工作目录的状态：  
**执行代码**  

`$ git status`

**命令行输出**

`$ git status`  
`# On branch master`  
`# Changes not staged for commit:`  
`#   (use "git add <file>..." to update what will be committed)`  
`#   (use "git checkout -- <file>..." to discard changes in working directory)`  
`#`  
`#	modified:   hello.rb`  
`#`  
`no changes added to commit (use "git add" and/or "git commit -a")`  

首先我们需要注意的是git知道hello.rb文件已经被修改，但是git并没有被告知暂存这些变化。

我们还需要注意的是命令行上的输出给了你提示接下来应该做什么。如果你想将这一些变化添加到版本库，请使用git add命令。或者git checkout命令可以消除这一些变化


