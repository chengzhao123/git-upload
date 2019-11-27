# 代码上传到GitHub(不是更新项目)
### 一般的流程是
```
touch README.md  //新建说明文件
git init //在当前项目中生成本地git管理，并建立一个隐藏.git项目
git add 文件名  //添加当前目录中的某个文件到索引
git commit -m "first commit" //提交到本地源码库，并附加提交注释
git remote add origin https://github.com/chape/test.git //添加到远程项目,别名为origin
git push -u origin master //把本地源码库push到github别名为origin的远程项目中，确认提交。
git remote rm origin //断开远程仓库连接
```
### 提交完成，查看repository
### 注意在提交的过程中是需要向远程仓库更新文件时需要：
```
git fetch origin
git merge origin/master
git push -u origin master
```
### 否则会报错： 
```
error: failed to push some refs to 'https://github.com/budaxxx/InAppSetingsKitDemo.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Merge the remote changes (e.g. 'git pull')
hint: before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
```
在执行命令：git remote add origin https://github.com/chape/test.git时可能会出现
fatal: remote origin already exists.
```
### 解决办法如下：
* 先输入 git remote rm origin
* 再输入 git remote add origin git@github.com:djqiang/gitdemo.git 就不会报错了
### 如果输入 git push origin master
提示出错信息：error:failed to push som refs to .......解决办法如下：
* 先输入$ git pull origin master //先把远程服务器github上面的文件拉下来
* 再输入$ git push origin master
* 如果出现报错 fatal: Couldn't find remote ref master或者fatal: 'origin' does not appear to be a git repository以及fatal: Could not read from remote repository.
* 则需要重新输入$ git remote add origingit@github.com:djqiang/gitdemo.git

使用git在本地创建一个项目的过程：
* $ makdir ~/hello-world    //创建一个项目hello-world
* $ cd ~/hello-world       //打开这个项目
* $ git init             //初始化 
* $ touch README
* $ git add README        //更新README文件
* $ git commit -m 'first commit'     //提交更新，并注释信息“first commit”
* $ git remote add origin git@github.com:defnngj/hello-world.git     //连接远程github项目  
* $ git push -u origin master     //将本地项目更新到github项目上去

git常用命令总结：
* git push origin master //把本地源码库push到Github上
* git pull origin master //从Github上pull到本地源码库
* git config --list //查看配置信息
* git status //查看项目状态信息
* git branch //查看项目分支
* git checkout -b host//添加一个名为host的分支
* git checkout master //切换到主干
* git merge host //合并分支host到主干
* git branch -d host //删除分支host
* git remote -v 查看当前在哪一个远程仓库

