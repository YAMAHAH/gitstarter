1.初始化好中央仓库
    git init
2.所有人克隆中央仓库
    git clone 
3.A协同开发
    git status # 查看本地仓库的修改状态
    git add # 暂存文件
    git commit # 提交文件
4.B协同开发
    git status # 查看本地仓库的修改状态
    git add # 暂存文件
    git commit # 提交文件
5.A发布功能
    git push origin master
    因为中央仓库，没有更新过，所以发布成功
6.B发布功能
    git pull --rebase origin master
    git pull合并上游的修改到自己的仓库中，--rebase选项告诉Git把B的提交移到同步了中央仓库修改后的master分支的顶部，
	如果没有此选项，提交历史会以一个多余的『合并提交』结尾

    合并时可能出现冲突，那么解决冲突后提交解决冲突的文件
    git add
    然后告诉git继续执行
    git rebase --continue
    如果解决不了，则可以恢复到rebase前的状态
    git rebase --abort

    解决冲突并提交成功后可以推送到远程仓库
    git push origin master
