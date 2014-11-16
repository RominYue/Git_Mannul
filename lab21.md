##更多结构
###目标
在版本库中加入另一个文件
##01 现在添加一个Rakefile
**文件 Rakefile**

	#!/usr/bin/ruby -wKU

	task :default => :run

	task :run do
  	   require './lib/hello'
	end
**执行代码**

`$ git add Rakefile`  
`$ git commit -m "Added a Rakefile"`

**执行代码**

`$ rake`

**命令行输出**

	$ rake
	Hello, World!
