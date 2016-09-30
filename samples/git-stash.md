1.把当前工作现场保存

    git stash

2.查看保存的工作现场

    git stash list

3.恢复工作现场

    git stash apply  //恢复最近的工作现场，但不删除

    git stash apply stash@{0} //恢复指定的工作现场

    git stash drop //删除保存的工作现场

    git stash drop stash@{0}  //删除指定的工作现场

    git stash pop //恢复工作现场，并且删除