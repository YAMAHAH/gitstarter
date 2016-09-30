1.新建一个分支，并且代码和服务器中代码同步

   git checkout origin/xxx -b temp  

2.保证新建的temp分支代码是最新

  git pull

3.当你新建分支后，系统会自动checkout到temp分支上，此时

  git checkout  new

4.合并代码，并整理

  git rebase  temp  //会将temp分支的代码合并过来，并按照提交的顺序排序

5.因为顺序是重新整理的，所以肯定会出现冲突

6.解决冲突，最后 git add * ，但不许要git commit

7.解决后，执行 git rebase --continue

8.重新提交代码： git push
