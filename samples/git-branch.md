1.创建分支

   git branch xxxxx

   git branch //显示分区

2.切换分支

   git checkout xxxxxx

3.在分支上修改，提交

    git commit -am xxxxxx

4.切换到主分支

   git checkout master //切换到主分支

5.在主分支上提交

   git commit -a

6.合并分支到主干道

   git merge xxxxxx 
     
7.提交该分支到远程仓库

   git push origin xxx

8.测试从远程获取xxx

   git pull origin xxx

9.合并完分支后，对分支进行删除

git branch -d xxxxxx  -d，表示“在分支已经合并到主干后删除分支”

git branch -d xxxxxx  -D，则表示“不论如何都删除分支”
