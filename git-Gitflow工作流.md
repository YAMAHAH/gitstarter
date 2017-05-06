1.假设已经创建了中央仓库，复制一个开发分支
    git branch develop
    git push -u origin develop
2.克隆开发分支
    git clone ssh://user@host/path/to/repo.git
    git checkout -b develop origin/develop

3.A基于开发分支创建功能分支
    git checkout -b some-feature develop
    编辑、暂存、提交：
    git status
    git add
    git commit
4.A完成功能开发
    git pull origin develop //拉取最新的开发分支
    git checkout develop //切换到开发分支
    git merge some-feature  //合并功能分支到开发分支
    git push //推送到远程仓库
    git branch -d some-feature //删除功能分支
5.A准备发布
    git checkout -b release-0.1 develop //基于开发分支创建发布分支，此时不可增加功能，只能修改BUG，增加文档等

6.A完成发布
    git checkout master //切换到master分支
    git merge release-0.1 //合并分支到master
    git push //推送到远程仓库
    git checkout develop //切换到develop分支
    git merge release-0.1 //合并分支到develop
    git push //远程推送
    git branch -d release-0.1 //删除分支

    git tag -a 0.1 -m "Initial public release" master //发布标标签
    git push --tags //推送标签到服务器

7.维护分支
    git checkout -b issue-#001 master //从master分支创建一个BUG分支
    # Fix the bug  编辑、暂存、提交修复BUG

    git checkout master //切换到master分支
    git merge issue-#001 //合并bug分支到master分支
    git push //推送到远程仓库
    
    //把bug分支合并到develop分支
    git checkout develop //切换到develop分支
    git merge issue-#001 //合并bug分支
    git push //推送到远程仓库
    git branch -d issue-#001 //删除分支