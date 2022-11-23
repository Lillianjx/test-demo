git命令学习：
1、git安装后第一件事：
指定username和useremail

Lilli@DZ MINGW64 ~/Desktop/新建项目-demo (master)
$ git config --global user.email "lillianlx_li@163.com"

Lilli@DZ MINGW64 ~/Desktop/新建项目-demo (master)
$ git config --global user.name "lillian"


2、在github上获取别人的项目：
git clone 链接地址

3、自己创建项目：
在本地创建项目文件夹之后，初始化
（可以在创建的文件夹里面打开git终端）


$ git init	//初始化，生成.git文件

4、添加文件，提交到版本库：

$ git add .	//添加所有文件
$ git add main.py	//添加指定文件
$ git commit -m "备注信息：如完成功能1"	//提交

5、查看提交记录：
$ git log	//查看提交历史记录，从最近到最远，可以看到3次

6、代码有改动跑不通了。恢复上一个版本：
$ git checkout HEAD main.py

明日学习：
7、远程仓库
$ ssh-keygen -t rsa -C "youremail@example.com"	//创建SSH Key
$ git remote add origin git@github.com:Daisy/AKgit.git	//关联
$ git push -u origin master	//将本地内容推送到远程仓库（第一次）
$ git push origin master	//将本地内容推送到远程仓库（之后）
$ git remote -v        //查看远程仓库信息
$ git remote rm origin	//删除远程仓库（解绑）
$ git clone git@github.com: Daisy/AKgit.git	//克隆远程仓库
//克隆之后使用和查看
$ cd gitskills
$ ls
$ git remote	//查看远程库的信息
$ git remote -v	//查看远程库的详细信息

8、多人协作
$ git checkout -b dev	//创建并切换到分支dev
//创建并切换到分支dev，同上
$ git branch dev	//创建
$ git checkout dev	//切换
//新版本
$ git switch -c dev	//创建并切换到分支dev
$ git switch master	//直接切换分支
$ git branch		//查看当前分支
$ git merge dev	（--no-ff）(-m)//合并，把dev分支的工作成果合并到master分支上
$ git branch -d dev	//删除dev分支 
$ git stash	//将现场储藏起来
$ git stash list	//查看储存的工作现场
//恢复和删除
$ git stash apply
$ git stash drop
//恢复并删除
$ git stash pop
$ git cherry-pick 4c805e2	//复制修改
$ git push origin master（dev）	//推送分支
$ git checkout -b dev origin/dev	//创建远程origin的dev分支到本地
$ git pull	//抓取分支（解决冲突）
$ git branch --set-upstream-to=origin/dev dev//指定本地与远程dev的链接
$ git rebase	//把本地未push的分叉提交历史整理成直线