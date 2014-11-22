## pulling shared changes
###目标
学习如何从共享版本库中提交修改  
**执行代码**

`$ cd ../cloned_hello`  

**执行代码**

`$ git remote add shared ../hello.git`  
`$ git branch --track shared master`  
`$ git pull shared master`  
`$ cat README`
