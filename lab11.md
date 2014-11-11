##别名
###目标
学习如何设定git命令的别名与缩写
##01 常用别名
git status, git commit, git checkout 是常用的命令，因此对它们设定别名是很有用处的。  
在你的家目录的.gitconfig文件中加入以下内容：

	[alias]
 	 co = checkout
 	 ci = commit
 	 st = status
 	 br = branch
 	 hist = log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short
 	 type = cat-file -t
 	 dump = cat-file -p

在这里我们包括了commit命令，status命令。还包括以前的log命令。checkout命令稍后提及。

当这一些别名被定义在.gitconfig文件中时，当你想要输入git checkout 的时候仅仅只需要输入 git co 就可以了。同样也适用于git st 和 git ci。当你输入git hist的时候就可以避免很长的git log命令了。
##02 在你自己的.gitconfig文件定义hist别名
大部分的时候，我将会输入命令的全称。唯一的例外就是当我想观看历史记录的时候，我将使用上述定义的git hist 命令。在继续学习之前确保你的.gitconfig文件中已经有了hist 别名。
##03 type and dump
我们添加了一些以前从没见过的命令的别名。git branch命令将会马上提及。git cat-file命令也很有用，不久之后也会提及。
##04 Shell 别名
注意：本章节只适用于遵循posix标准的shell。Windows用户和非posix shell用户可自由选择是否跳过本章节。

如果你的shell支持修改别名或缩写的话，那么你就可以做一些改变。  

**文件 .profile**  

	alias gs='git status '
	alias ga='git add '
	alias gb='git branch '
	alias gc='git commit'
	alias gd='git diff'
	alias go='git checkout '
	alias gk='gitk --all&'
	alias gx='gitx --all'

	alias got='git '
	alias get='git '
那么go是git checkout 的 别名，这样是不是很爽！我就可以直接输入

`$ go <branch>`

来检查特定的分支。  
