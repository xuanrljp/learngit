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
    $ git rm --cached <file_name>           //删除stage的文件
    $ git checkout -- file                  //从stage恢复文件到工作区
    $ git checkout <commit_id> <file_name>  //回退指定版本
    $ git reset --hard <commit_id>          //回退指定版本
    $ git reset --hard HEAD^                //回退到上一个 版本


##远程关联

####关联到远程克隆
    $ git remote add origin url
####从远程克隆
    $ git clone url
####查看remote信息
    $ git remote -v


##分支管理

####查看分支
    $ git branch        //本地分支一览
    $ git branch -r     //远程分支一览
    $ git branch -a     //本地 + 远程分支一览
####切换分支
    $ git checkout <branch>
####创建分支
    git branch <branch>
    $ git checkout -b <branch>   //git branch <branch> + git checkout <branch> //创建+切换
    $ git checkout -b <branch> origin/<remote_branch>  //checkout branch from remote
####合并分支
    $ git merge 目标<branch>     //合并指定分支到当前分支
####删除分支
    $ git branch -d <branch>
####修改分支
    $ git branch -m <branch>     //修改当前分支名


##标签管理

####查看标签
    $ git tag
    $ git tag -l 'v1.4.2.*'                 //匹配符搜索
    $ git show v1.4                         //查看具体标签信息
####创建标签
    $ git tag -a <tagname>
    $ git tag -a <tagname> -m 'comment'     //含注释的标签
    $ git tag -a <tagname> <commit_id>      //后期加补标签
####删除标签
    $ git tag -d <tag>
####checkout标签
    //签出并创建分支
    $ git checkout -b <branch> refs/tags/<tagname>
    //签出但不创建分支
    $ git checkout refs/tags/<tagname>
####远程协作
    $ git push origin <tagname>        //注意 git push不会把标签上传到远程
    $ git push origin --tags           //推送所有本地新增标签
    $ git push origin :<tagname>       //push本地删除标签
    $ git pull --tags                  //从远程取得标签


##冲突解决


##Submodule


##Git服务器


##团队协作