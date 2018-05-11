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
