# OtcOne
sublime连接github


######git的简单使用######
github文件夹中有多个项目，OtcOne、fe等项目


1.进入到项目的父目录<br>
cd /F/学习/13其他职位技术/web前端开发/github/ <br>
git init --初始化，生成.git隐藏文件类似.svn

2.项目先clone下来<br>
git clone git@github.com:gugujingling/fe.git

3.编辑or新增or删除，进入到项目目录<br>
git add .

4.提交前，最好pull一下，保持与服务器版本一致，<br>
git pull origin master

5.commit提交，写说明<br>
git commit -m 'first_commit'

6.push上去<br>
git push origin master



##########git命令###########

1.add<br>
git add <path> --主要用于把要提交的文件的信息添加到索引库中<br>
git add -i [<path>]  --查看<path>中被所有修改过或已删除文件但没有提交的文件，即索引库中的文件
2.rm<br>
git rm -f --cached fe或者readme.md  ----强制删除暂存区的文件或文件夹
