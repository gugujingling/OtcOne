############Git命令详解##################
<br>
 F1  ：执行info指令，查询指令相关信息，会要求您输入欲查询的名称。<br>
 F2  ：执行cat指令，列出文件内容。<br>
 F3  ：执行gitview指令，观看文件内容。<br>
 F4  ：执行vi指令，编辑文件内容。<br>
 F5  ：执行cp指令，复制文件或目录，会要求您输入目标文件或目录。<br>
 F6  ：执行mv指令，移动文件或目录，或是更改其名称，会要求您输入目标文件或目录。<br>
 F7  ：执行mkdir指令，建立目录。<br>
 F8  ：执行rm指令，删除文件或目录。<br>
 F9  ：执行make指令，批处理执行指令或编译程序时，会要求您输入相关命令。<br>
 F10 ：离开git文件管理员。<br>

##Git是一个免费的、分布式的版本控制工具，速度快的源代码管理工具##
<br>

一. Git 通常有两种方式来进行初始化:<br>

1.git clone: 这是较为简单的一种初始化方式，当你已经有一个远程的Git版本库，只需要在本地克隆一份
<br>
	例如：git clone git://github.com/someone/some_project.git  some_project 
	上面的命令就是将'git://github.com/someone/some_project.git'这个URL地址的远程版本库完全克隆到本地some_project目录下面，
	some_project目录名可以不写，默认与some_project.git名一致。
<br>
2.git init和git remote：这种方式稍微复杂一些
<br>
	当你本地创建了一个工作目录，你可以进入这个目录，使用'git init'命令进行初始化，Git以后就会对该目录下的文件进行版本控制，这时候如果你需要将它放到远程服务器上，可以在远程服务器上创建一个目录，并把 可访问的URL记录下来，此时你就可以利用'git remote add'命令来增加一个远程服务器端
<br>
	例如：git remote add other-origin git://github.com/someone/another_project.git
<br>
	上面的命令就会增加URL地址为'git: //github.com/someone/another_project.git'，名称为other-origin的远程服务器，以后提交代码的时候只需要使用 other-origin别名即可
<br>	
	之后就是修改提交远程服务器操作了：
		git add .
		git pull other-origin master
		git commit -m 'first_commit'
		git push other-origin master

二.Git的基本命令<br>
	现在我们有了本地和远程的版本库，让我们来试着用用Git的基本命令：
<br>
	
1.git pull：从其他的版本库（既可以是远程的也可以是本地的）将代码更新到本地，例如：'git pull origin master'就是将origin这个版本库的代码更新到本地的master主枝，该功能类似于SVN的update
<br>
2.git add：是将当前更改或者新增的文件加入到Git的索引中，加入到Git的索引中就表示记入了版本历史中，这也是提交之前所需要执行的一步，例如'git add app/model/user.rb'就会增加app/model/user.rb文件到Git的索引中，该功能类似于SVN的add
<br>
3.git rm：从当前的工作空间中和索引中删除文件，例如'git rm app/model/user.rb'，该功能类似于SVN的rm、del，再如git rm -f --cached fe或者readme.md，该功能强制删除暂存区的文件或文件夹
<br>
4.git commit：提交当前工作空间的修改内容，类似于SVN的commit命令，例如'git commit -m 'story add user model'，提交的时候必须用-m来输入一条备注信息，该功能类似于SVN的commit
<br>
5.git push：将本地commit的代码更新到远程版本库中，例如'git push origin'就会将本地的代码更新到名为orgin的远程版本库中
<br>
6.git log：查看历史日志，该功能类似于SVN的log
<br>
7.git revert：还原一个版本的修改，必须提供一个具体的Git版本号，例如'git revert bbaf6fb5060b4875b18ff9ff637ce118256d6f20'，Git的版本号都是生成的一个哈希值
<br>
<br>
上面的命令几乎都是每个版本控制工具所公有的，下面就开始尝试一下Git独有的一些命令：
<br>
<br>
8.git branch：对分支的增、删、查等操作，例如'git branch new_branch'会从当前的工作版本创建一个叫做new_branch的新分支，'git branch -D new_branch'就会强制删除叫做new_branch的分支，'git branch'就会列出本地所有的分支
<br>
9.git checkout：Git的checkout有两个作用，其一是在不同的branch之间进行切换，例如'git checkout new_branch'就会切换到new_branch的分支上去；另一个功能是还原代码的作用，例如'git checkout app/model/user.rb'就会将user.rb文件从上一个已提交的版本中更新回来，未提交的内容全部会回滚
<br>
10.git rebase：rebase命令执行后，实际上是将分支点从分支开始的位置移到主支的最后，这样分支也就具有了主支所有的功能
<br>
11.git reset：将当前的工作目录完全回滚到指定的版本号，假设如下图，我们有A-G五次提交的版本，其中C的版本号是 bbaf6fb5060b4875b18ff9ff637ce118256d6f20，我们执行了'git reset bbaf6fb5060b4875b18ff9ff637ce118256d6f20'那么结果就只剩下了A-C三个提交的版本
<br>
12.git stash：将当前未提交的工作存入Git工作栈中，时机成熟的时候再应用回来，这里暂时提一下这个命令的用法，
后面在技巧篇会重点讲解
<br>
13.git config：利用这个命令可以新增、更改Git的各种设置，例如'git config branch.master.remote origin'就将master的远程版本库设置为别名叫做origin版本库，后面在技巧篇会利用这个命令个性化设置你的Git，为你打造独一无二的 Git
<br>
14.git tag：可以将某个具体的版本打上一个标签，这样你就不需要记忆复杂的版本号哈希值了，例如你可以使用'git tag revert_version bbaf6fb5060b4875b18ff9ff637ce118256d6f20'来标记这个被你还原的版本，那么以后你想查看该版本时，就可以使用 revert_version标签名，而不是哈希值了
<br>

