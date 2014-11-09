##暂存这些变化
###目标
学习如何暂存修改与变化
##01 添加修改
现在应该告诉git来暂存着一些变化，并检查状态  
**执行代码**

`$ git add hello.rb`  
`$ git status`

**命令行输出**

`$ git add hello.rb`  
`$ git status`  
`# On branch master`  
`# Changes to be committed:`  
`#   (use "git reset HEAD <file>..." to unstage)`  
`#`  
`#	modified:   hello.rb`  
`#`  

hello.rb文件的变化已经被暂存在git中。这意味着git已经知晓这种文件修改，但是这种修改还没有被版本库永久地记录。下面的commit操作将会记录这种变化

如果你决定不想提交该变化，状态信息提醒你可以使用git reset 命令不暂存该变化。