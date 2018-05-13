# git-guide
git的基础知识总结

1.创建一个版本库： 先到自己所在的文件中，然后git init创建仓库。

2.编写好文件以后用 git add readme.txt 告诉 git.把文件添加到仓库.

git commit -m "修改的文件的说明"

git status
时刻掌握仓库当前的状态。

git diff readme.txt  如果不记得当时是如何修改的文件可以进行查看。

git add readme.txt  再提交给仓库

git log --pretty=oneline --abbrev-commit   如果改的多了自己不记得了，输入后会看到每一次改动的信息。

git reset --hard HEAD^   当前版本退回到上一个版本

查看文件的内容是不是上一个版本   cat readme.txt

git reset --hard 343234(想到的地方的代号)  commit id     get reset --hard commit_id

git reflog  是用来记录你每一次的命令。

git checkout --file.txt    当改错了工作区某个文件的内容，想直接丢弃工作区的修改时。

git reset HEAD file   然后 git checkout file  

git rm file.txt     想要直接删除文件，不可修复。

rm fiel.txt  删除以后还可以修复->  git checkout -- file.txt  修复


需要自己的电脑和github上面关联时的操作方法：

1.创建SSH Keys

ssh-keygen -t rsa -C "niujiawei1994@yahoo.co.jp"

一路回车设置微默认值

cd .ssh   进入到.ssh目录   

cat id_rsa.pub  打开文件复制文件内容

登录github, 打开account settings, SSH Keys，点击 Add SSH Keys, 填入任意title, 在 Key 栏粘贴刚才复制的内容。点击 Add Keys.

登录github  create a new repo创建新的仓库

将本地仓库和他关联     git remote add origin git@github.com:jiaweiniu/learngit.git

然后把本地仓库的内容推送到gituhb仓库      git push -u origin master (第一次提交需要加 -u)

再次提交  git push origin master

查看分支    git branch

创建分支    git branch name

切换分支    git checkout name

创建+切换分支    git checkout -b name

合并某分支到当前分支   git merge name 

删除分支     git branch -d name

查看分支合并图    git log --graph

当手头工作没有做完时，先 git stash, 保存内容， 恢复时， git stash pop 

git stash list  查看stash内容

需要开发新的内容的时候，新建一个分支开发，用过以后合并新分支然后删除。

如果需要丢弃一个没有被合并过的分支，     git branch -D name  进行强行删除。



多人协调工作模式：

1.用 git push origin branch-name 推送自己的修改

2.若推送失败，是因为远程分支比你的本地更新，需要先 git pull 合并

3.若 git pull 提示 no tracking information , 说明本地分支和远程分支的链接关系没有创建，用命令

 git branch --set-upstream branch-name origin/branch-name
 
 4.git push origin branch-name  推送成功
 
 查看远程库信息   git remote -v
 
 本地新建的分支如果不推送到远程，对其他人是不可见的
 
 git tag name 用于创建一个标签
 
 git tag commitid 可以指定为一个id 创建
 
 git tag -a tagname -m "信息"  可以指定标签信息
 
 git tag 可以查看所有标签
 
git show name  查看指定标签的信息 

删除标签  git tag -d tagname     删除指定版本

推送某个标签到远程， git push origin tagname 

一次性将所有标签推送到远程    git push origin --tags

将已经推送到远程的标签删除      

1. 先从本地删除    git tag -d v0.9

2. 从远程删除      git push origin :refs/tags/v0.9


同时关联 github 和 码云  方法：

1.先删除已关联的名为 origin的远程库  git remote rm origin

2.先关联github 的远程库   git remote add github git@github.com:jiaweiniu/learngit.git       注意远程库的名字是github 而不是origin了！！

3.再关联码云的远程库   git remote add gitee git@gitee.com:username/learngit.git          注意远程库的名字是gitee, 不是origin

4. 现在查看远程库的消息     git remote -v    就可以看到两个远程库了

5. 推送到github,    git push github master 

6. 推送到码云    git push gitee master   



配置别名  

git config --global alias.st status      用st 代表 status ,代码会变得简洁。

git config --global alias.co checkout

git config --global alias.ci commit

git config --global alias.br branch

当前用户的配置文件都是在主目录下的隐藏文件中  .gitconfig 中，配置别名可以直接修改这个文件，改错了也可以直接删除重新配置
