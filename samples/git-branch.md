1.创建分支

   git branch xxxxx

   git branch //显示分区

   git checkout -b xxxxxx //从origin/master创建分支并切换分支

   git checkout origin/master -b dev   //从已有的分支创建新的分支(如从master分支),创建一个dev分支

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

10.设置git push,pull默认的提交获取分支,方便使用git push 提交信息或git pull获取信息

    git branch --set-upstream-to=origin/dev

    git branch --unset-upstream master //取消对master的跟踪
