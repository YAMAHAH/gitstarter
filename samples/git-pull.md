1.指定pull当前分支的upstream:

    git branch --set-upstream-to=origin/<branch> xxx

    Or  git push --set-upstream origin xx 

2.指定某个分支的默认merge操作(xxx为分支名称)

    config文件方式:

        [branch "xxx"]

        remote = origin

        merge = refs/heads/xxx

   command-line:
   
      git config branch.develop.merge refs/heads/xxx