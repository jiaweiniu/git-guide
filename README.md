# git-guide
git的基础知识总结

1.创建一个版本库： 先到自己所在的文件中，然后git init创建仓库。

2.编写好文件以后用 git add readme.txt 告诉 git.把文件添加到仓库.

git commit -m "修改的文件的说明"

git status
时刻掌握仓库当前的状态。

git diff readme.txt  如果不记得当时是如何修改的文件可以进行查看。

git add readme.txt  再提交给仓库

git log   如果改的多了自己不记得了，输入后会看到每一次改动的信息。

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
