# GIT常用指令
## 基础
1. 工作区 -> 暂存区(stage/index) -> 版本库(master) -> 远程仓库
## 创建
1. 新建文件夹dir
2. git init ：变成Git可管理的仓库
3. 新建编辑文件 demo.txt
4. git add demo.txt：添加到暂存区
5. git commit -m "提交说明"：提交到仓库

## 修改删除 
1. 修改文件demo.txt
2. git status：查看文件当前的状态
3. git diff demo.txt：对比该文件前后的不同
> -表示源文件，+表示目标文件

> -1,3表示源文件从第1行开始的3行，+1,2表示目标文件从第1行开始的2行

> 前面有空格表示无修改，'-'表示在源文件的基础上删除，'+'表示在源文件的基础上添加   

4. git rm demo.txt：删除文件
## 回退
1. git log：历史记录（commit id）
2. git reset --hard HEAD^：回退到上一个版本
> HEAD表示当前版本，HEAD^为上一个版本，HEAD^^，HEAD~100依次类推

3. git reset --hard 1094a：返回最新版本
4. cat demo.txt：查看内容
5. git reflog；记录每一次命令
## 撤销修改
1. when改乱工作区内容&直接丢弃工作区修改:
   
   `git checkout -- demo.txt`
2. when改乱工作区内容&添加至暂存区：
   
   `git reset HEAD demo.txt`
   `git checkout -- demo.txt`
3. when已提交到版本库&撤销：
   **版本回退，前提是没有推送到远程库push
## 远程仓库（先本地后远程）
1. github创建仓库
2. git remote add origin 仓库地址：关联远程库
3. git add.  /  git commit -m ""
4. git push -u origin master
> 首次推送master分支内容到远程：-u
> 之后提交不需要
## 远程仓库（先远程后本地，推荐）
1. 创建库，readme.md
2. git clone 
## 分支管理

**完成某任务时，推荐使用分支，完成后再合并删除，更安全;**

**在dev分支上分工，最后更新版本合并主分支；**

**开发一个新功能，新建一个分支feature**

**分支：master、dev、bug、feature**
1. git checkout -b dev：新建分支dev，并切换到该分支（git branch dev：新建分支）
2. git branch：查看分支，*表示当前分支，之后的操作也在该分支进行
3. git checkout master：切换回mater分支
4. git merge dev：dev合并到主分支，此时应位于主分支（不能看出合并历史）
5. git branch -d dev：删除分支
6. 解决分支冲突，需手动编辑失败的文件
7. git push origin 分支名：本地推送分支
8. git tag：打标签

参考资料：
[廖雪峰git教程](https://www.liaoxuefeng.com/wiki/896043488029600)