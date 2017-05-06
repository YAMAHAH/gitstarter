1.A创建基于master功能分支
    git checkout -b marys-feature master
    编辑、暂存和提交修改，按需要提交以实现功能：
    git status
    git add
    git commit
    把功能分支推送到远程仓库
    git push -u origin marys-feature
    -u选项设置本地分支去跟踪远程对应的分支。设置好跟踪的分支后，A就可以使用git push命令省去指定推送分支的参数。
2.A发送pull request，B接收到请求，A和B讨论功能，如要修改，A直接执行操作，当然B也可以把功能分支拉下来修改
    要再做修改，A用和功能第一个迭代完全一样的过程。编辑、暂存、提交并push更新到中央仓库
3.A发布功能
首先要检出master分支并确认是它是最新的。
    git checkout master 
    git pull    
然后执行git pull origin marys-feature合并marys-feature分支到和已经和远程一致的本地master分支。你可以使用简单git merge marys-feature命令，但前面的命令可以保证总是最新的新功能分支。
    git pull origin marys-feature
最后更新的master分支要重新push回到origin。
    git push