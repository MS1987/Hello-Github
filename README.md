#GitHub是什么？  #
GitHub是一个基于Git的代码托管仓库，你可以在上面进行公开代码免费的存放，也可进行付费的私密代码存放。
#那Git是什么  #
Git是一个分布式版本管理工具,可能有人想起我们经常使用的svn等，他们有类似的地方，但也有比较大的区别。

- 相同点：都可以进行常见的版本控制，例如版本check、commit、branch等等

- 不同点：Git是分布式管理，SVN是集中式管理。
![](https://i.imgur.com/R2WlSEY.png)

##不同点在使用时主要有什么影响  ##
研发人员应该比较清楚，我们的SVN需要有个服务器集中存放所有版本代码，每个人的电脑上各自安装客户端进行版本的检出提交操作，这样有个问题是当服务器出现故障，或者网络不通的情况，其他电脑都无法进行任何Check、commit、branch等操作，这是因为所有电脑只是存放了不同版本的快照，并没有整个版本内容。
但Git不一样，他是分布式管理，意思是只要clone了版本的电脑都有完整的版本镜像，可能大家会问，那我们使用github不也需要服务器吗？github服务器只是方便大家交流，并不是版本保存的必要设备，比如说marlin的github，其实哪怕服务器挂掉了，只要你电脑本地有clone过，你都可以在本地进行commit、branch等操作的。

#安装Git #
直接到官网下载git：[https://git-scm.com/downloads](https://git-scm.com/downloads "Git")，安装非常简单。
#使用Git  #
安装git后，会有gui程序和命令行程序，两者都可以使用，但gui本质上也是执行命令行，以下都采用命令行来演示，打开安装的“git cmd”命令窗口
##检出仓库  ##


- 执行如下命令以创建一个本地仓库的克隆版本：

	git clone /path/to/repository


- 如果是远端服务器上的仓库，你的命令会是这个样子：
	
	git clone username@host:/path/to/repository

**工作流**


- 你的本地仓库由 git 维护的三棵“树”组成。
- 第一个是你的 工作目录，它持有实际文件；
- 第二个是 暂存区（Index），它像个缓存区域，临时保存你的改动；
- 最后是 HEAD，它指向你最后一次提交的结果。
![工作流](https://i.imgur.com/ydqFAvB.png)

## 添加和提交 ##
如果新增了文件你可以提出更改（把它们添加到暂存区），使用如下命令：

    git add <filename>
    git add *
这是 git 基本工作流程的第一步；
使用如下命令以实际提交改动：

	git commit -m "代码提交log"
现在，你的改动已经提交到了 HEAD，但是还没到你的远端仓库。
## 推送改动 ##
你的改动现在已经在本地仓库的 HEAD 中了。执行如下命令以将这些改动提交到远端仓库：

	git push origin master
可以把 master 换成你想要推送的任何分支。

如果你还没有克隆现有仓库，并欲将你的仓库连接到某个远程服务器，你可以使用如下命令添加：

	git remote add origin <server>
如此你就能够将你的改动推送到所添加的服务器上去了。

## 分支 ##
分支是用来将特性开发绝缘开来的。在你创建仓库的时候，master 是“默认的”分支。在其他分支上进行开发，完成后再将它们合并到主分支上。


----------
创建一个叫做“feature_x”的分支，并切换过去：

	git checkout -b feature_x
切换回主分支：

	git checkout master
再把新建的分支删掉：

	git branch -d feature_x
除非你将分支推送到远端仓库，不然该分支就是 不为他人所见的：

	git push origin <branch>
## 更新与合并 ##
要更新你的本地仓库至最新改动，执行：

	git pull
以在你的工作目录中 获取（fetch） 并 合并（merge） 远端的改动。
要合并其他分支到你的当前分支（例如 master），执行：

	git merge <branch>
在这两种情况下，git 都会尝试去自动合并改动。遗憾的是，这可能并非每次都成功，并可能出现冲突（conflicts）。 这时候就需要你修改这些文件来手动合并这些冲突（conflicts）。改完之后，你需要执行如下命令以将它们标记为合并成功：

	git add <filename>
在合并改动之前，你可以使用如下命令预览差异：

	git diff <source_branch> <target_branch>

# 创建自己的GitHub#

## 使用github的桌面工具