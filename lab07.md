##暂存和提交
git中相对独立的暂存步骤，阐释这样的哲学思想：你可以先完成其他的事情直到你需要处理这一些事务。你可以一直在你的工作目录中做一些修改，然后当你想要版本控制的时候，git允许你用简短的几行commit指令记录你所有的修改。  
比如，假设你现在编辑了三个文件(a.rb,b.rb,c.rb)。现在你想提交所有的修改，但是你希望关于a.rb和b.rb的修改是一个单一的提交。但是c.rb
和前面两个文件没有逻辑上的关联，它也应该是一个独立的提交。你应该这么做：  

`$ git add a.rb`  
`$ git add b.rb`  
`$ git commit -m "Changes for a and b"`
  
`$ git add c.rb`  
`$ git commit -m "Unrelated change to c"`

通过分离暂存和提交的步骤，我们可以很容易地知道每一次commit都干了些什么工作。