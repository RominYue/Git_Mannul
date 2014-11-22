##搭建一个git服务器
###目标
学习如何搭建一个git服务器

有很多种方法可以在网上分享git版本库。
##01 搭建一个git服务器
**执行代码**

`$ # (From the work directory)`  
`git daemon --verbose --export-all --base-path=.`

现在，在另一台终端窗口上，进入你的工作目录

**执行代码**

`$ # (From the work directory)`
`$ git clone git://localhost/hello.git network_hello`
`$ cd network_hello`
`$ ls`