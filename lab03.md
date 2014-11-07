##创建一个工程
###目标  
学习如何从头开始创建一个git版本库
##01 创建名为"Hello,World"的一个程序文件
在一个空白工作目录下，创建名为"hello"的一个空目录，然后在该目录中创建一个名为"hello.rb"的文件，文件内容如下述。  
**执行代码**  

`$ mkdir hello`  
`$ cd hello`  

**文件: hello.rb**  

`puts "Hello, World"`
##02 创建版本库
你现在有了一个含有单个文件的目录。为了能够在该目录创建一个git版本库，运行 git init 命令  
**执行代码**  

`$ git init`  

**命令行输出**  

`$ git init`  
`Initialized empty Git repository in /Users/jim/working/git/git_immersion/auto/hello/.git/`
##03 将程序文件添加到版本库
现在我们将“hello world”文件添加到版本库  
**执行代码**  

`$ git add hello.rb`  
`$ git commit -m "First Commit"`  

你应该看到...  
**命令行输出**  

`$ git add hello.rb`  
`$ git commit -m "First Commit"`  
`[master (root-commit) 9416416] First Commit`
`1 files changed, 1 insertions(+), 0 deletions(-)`
`create mode 100644 hello.rb`