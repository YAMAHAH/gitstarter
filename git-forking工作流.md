1.开发者fork正式仓库

2.开发者克隆自己fork出来的仓库

    git clone https://user@bitbucket.org/user/repo.git
    
    //添加上游仓库地址，用于和正式仓库同步
    
    git remote add upstream https://bitbucket.org/maintainer/repo
    
3.开发者开发自己的功能，开发者可以像其它工作流一样的编辑代码、提交修改和新建分支

    git checkout -b some-feature //创建功能分支
    
    // Edit some code
    
    git commit -a -m "Add first draft of some feature"
    
    所有的修改都是私有的直到push到自己公开仓库中。如果正式项目已经往前走了，可以用git pull命令获得新的提交：
    
    git pull upstream master

    由于开发者应该都在专门的功能分支上工作，pull操作结果会都是快进合并。
    
4.开发者发布自己的功能

    git push origin feature-branch
    
    开发者要通知项目维护者，想要合并他的新功能到正式库中。发起Pull Request，弹出表单让你指定哪个分支要合并到正式仓库。一般你会想集成你的功能分支到上游远程仓库的master分支中。
    
5.项目维护者集成开发者的功能

    当项目维护者收到pull request，他要做的是决定是否集成它到正式代码库中。有二种方式来做：

    *直接在pull request中查看代码
    
    *pull代码到他自己的本地仓库，再手动合并
    
第一种做法更简单，维护者可以在GUI中查看变更的差异，做评注和执行合并。但如果出现了合并冲突，需要第二种做法来解决。这种情况下，维护者需要从开发者的服务端仓库中fetch功能分支，合并到他本地的master分支，解决冲突：


git fetch https://bitbucket.org/user/repo feature-branch

// 查看变更

git checkout master

git merge FETCH_HEAD

变更集成到本地的master分支后，维护者要push变更到服务器上的正式仓库，这样其它的开发者都能访问到：

git push origin master

注意，维护者的origin是指向他自己公开仓库的，即是项目的正式代码库。到此，开发者的贡献完全集成到了项目中。

6.开发者和正式仓库做同步

    git pull upstream master
