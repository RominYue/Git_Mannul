##新建一个分支
###目标
学习如何在版本库中新建一个分支
##01 新建一个分支
**执行代码**

`$ git checkout -b greet`  
`$ git status`

注意 git checkout -b 是下面的缩写

`$ git branch <branchname>`  
`$ git checkout <branchname>` 

##02 在greet分支上做修改：添加Greeter类
**文件 lib/greeter.rb**

	class Greeter
  	  def initialize(who)
    	@who = who
  	  end
  	  def greet
    	"Hello, #{@who}"
  	  end
	end
**执行代码**

`$ git add lib/greeter.rb`  
`$ git commit -m "Add greeter class"`  
##03 在greeter分支修改：修改主控程序
更新hello.rb文件使之可以调用greeter.rb文件。  
**文件 hello.rb**

	require 'greeter'

	# Default is World
	name = ARGV.first || "World"

	greeter = Greeter.new(name)
	puts greeter.greet
**执行代码**

`$ git add lib/hello.rb`  
`$ git commit -m "Hello uses Greeter"`  
##04 在greeter分支修改：更新Rakefile 文件
**文件 Rakefile**

	#!/usr/bin/ruby -wKU

	task :default => :run

	task :run do
  	  ruby '-Ilib', 'lib/hello.rb'
	end
**执行代码** 

`$ git add Rakefile`  
`$ git commit -m "Updated Rakefile"`
