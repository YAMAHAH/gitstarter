列出标签
$ Git tag # 在控制台打印出当前仓库的所有标签
$ git tag -l ‘v0.1.*’ # 搜索符合模式的标签

打标签
git标签分为两种类型：轻量标签和附注标签。轻量标签是指向提交对象的引用，附注标签则是仓库中的一个独立对象。建议使用附注标签。
# 创建轻量标签
$ git tag v0.1.2-light

# 创建附注标签
$ git tag -a v0.1.2 -m “0.1.2版本”

创建轻量标签不需要传递参数，直接指定标签名称即可。
创建附注标签时，参数a即annotated的缩写，指定标签类型，后附标签名。参数m指定标签说明，说明信息会保存在标签对象中。

切换到标签
与切换分支命令相同，用git checkout [tagname]
查看标签信息
用git show命令可以查看标签的版本信息：
$ git show v0.1.2

删除标签
误打或需要修改标签时，需要先将标签删除，再打新标签。
$ git tag -d v0.1.2 # 删除标签

参数d即delete的缩写，意为删除其后指定的标签。

$ git push origin --delete v0.1.2 # h删除远程服务器上的标签

给指定的commit打标签
打标签不必要在head之上，也可在之前的版本上打，这需要你知道某个提交对象的校验和（通过git log获取）。
# 补打标签
$ git tag -a v0.1.1 9fbc3d0

标签发布--git push不会将标签对象提交到git服务器，我们需要进行显式的操作：
$ git push origin v0.1.2 # 将v0.1.2标签提交到git服务器
$ git push origin –tags # 将本地所有标签一次性提交到git服务器

git tag 用于新建一个标签，默认为HEAD，也可以指定一个commit id；

git tag -a -m "blablabla..."可以指定标签信息；

git tag -s -m "blablabla..."可以用PGP签名标签；

命令git tag可以查看所有标签。
