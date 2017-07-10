1.使用git命令可以直接添加Submodule

    git submodule add git@github.com:jjz/pod-library.git pod-library

    还可以这样使用命令添加Submodule

    git add .gitmodules pod-ibrary

    git commit -m "pod-library submodule"

    git submodule init
    修改测试
2.修改子模块
    
    进入Submodule目录,查看状态
    
    git status
    
    提交子模块变动
        
        git commit -a -m'test submodule'

    推送子模块

      git push
    
    回到父目录,提交Submodule在父项目中的变动：

    git statuson branch master

    提交父目录的变动
    
    git commit -m'update submodule'

    推送父目录的变动到远程服务器

    git push

3.更新Submodule

    更新Submodule有两种方式:
    
    在父项目的目录下直接运行

    git submodule foreach git pull

    在Submodule的目录下面更新

    cd pod-library

    git pull

    可以看到在Submodule的目录中,使用git和单独的一个项目是一样的,注意更新Submodule的时候如果有新的commit id产生，需要在
    
    父项目产生一个新的提交，pod-libray文件中的 Subproject commit会变为最新的commit id。

4.clone Submodule

    1.采用递归参数 --recursive

        git clone git@github.com:jjz/pod-project.git --recursive

    2.先clone父项目，再初始化Submodule

        git clone git@github.com:jjz/pod-project.gitcd pod-project //克隆父项目

        git submodule init //初始化子模块

        git submodule update //更新子模块

5.删除Submodule

    git 并不支持直接删除Submodule需要手动删除对应的文件:

    cd pod-project

    git rm --cached pod-library
    
    rm -rf pod-library
    
    rm .gitmodules
    
    更改git的配置文件config:

    vim .git/config
    
    可以看到Submodule的配置信息：

    [submodule "pod-library"]
    
    url = git@github.com:jjz/pod-library.git

    删除submodule相关的内容,然后提交到远程服务器:

    git commit -a -m 'remove pod-library submodule'
