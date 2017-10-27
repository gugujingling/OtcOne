# OtcOne
sublime连接github


#########git的简单使用########
<br>
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



##########还原到指定版本##############
1.增加点内容
2.修改下内容

3.测试返回一个版本的修改。

    3为本地新增，未提交至版本库

    执行git revert指令

    预测结果 返回到github最新的commit二进制，本地文件第三条信息消失  

    实际结果 失败

#git revert e3b899484b86a2f834d5e9547af94f8e02b4986d

#error: Your local changes to the following files would be overwritten by merge:
#        asdf.txt
#Please commit your changes or stash them before you merge.
#Aborting
#fatal: revert failed

总结： 使用git revert 指令需确保目前版本与github版本一致， 然后返回任意指定的版本，3仍然存在，只是将指定的版本的修改还原

#############删除项目#################
1.

