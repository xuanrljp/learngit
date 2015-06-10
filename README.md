#学习git使用方法

##Git总览

####Git命令序列图
![overview](http://assets.osteele.com/images/2008/git-transport.png)
####File状态变化图
![filestatus](https://git-scm.com/figures/18333fig0201-tn.png)


##Git基础

####创建本地版本库
	$ git init
####查看工作区状态
    $ git status
####把工作区(workspace)文件放入暂存区(stage/index)
    $ git add files 
    $ git add .         //modified + new
    $ git add -u        //modified + deleted
    $ git add -A        //modified + +new + deleted
####把工暂存区(stage/index)文件提交到版本库
    $ git commit -m "comment"
    $ git commit -am "comment" //git add -u + git commit -m
####日志查看
    $ git log --oneline     //一行显示
    $ git reflog            //每一次命令的日志
####恢复修改
    $ git checkout -- file                  //从Stage恢复文件到工作区
    $ git checkout [commit_id] [file_name]  //回退指定版本
    $ git reset --hard [commit_id]          //回退指定版本
    $ git reset --hard HEAD^                //回退到上一个 版本


##远程关联

####关联到远程克隆
    $ git remote add origin url
####从远程克隆
    $ git clone url
####查看remote信息
    $ git remote -v


##分支管理

####查看当前所有分支
    $ git branch        //本地分支一览
    $ git branch -r     //远程分支一览
    $ git branch -a     //本地 + 远程分支一览
####切换分支
    $ git checkout [branch]    
####创建然后切换到该分支
    $ git checkout -b [branch]   //git branch [branch] + git checkout [branch]
####合并指定分支到当前分支
    $ git merge 目标[branch]
####删除分支
    $ git branch -d [branch]
####分支名变更
    $ git branch -m [branch]     //修改当前分支名


##标签管理


##冲突解决


##Submodule


##Git服务器


##团队协作