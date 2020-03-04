# GitHub是什么？
GitHub是一个基于Git的代码托管仓库，你可以在上面进行公开代码免费的存放，也可进行付费的私密代码存放。
#  #那Git是什么
Git是一个分布式版本管理工具,可能有人想起我们经常使用的svn等，他们有类似的地方，但也有比较大的区别。

- 相同点：都可以进行常见的版本控制，例如版本check、commit、branch等等

- 不同点：Git是分布式管理，SVN是集中式管理。
![](https://i.imgur.com/R2WlSEY.png)

##  ##不同点在使用时主要有什么影响
研发人员应该比较清楚，我们的SVN需要有个服务器集中存放所有版本代码，每个人的电脑上各自安装客户端进行版本的检出提交操作，这样有个问题是当服务器出现故障，或者网络不通的情况，其他电脑都无法进行任何Check、commit、branch等操作，这是因为所有电脑只是存放了不同版本的快照，并没有整个版本内容。
但Git不一样，他是分布式管理，意思是只要clone了版本的电脑都有完整的版本镜像，可能大家会问，那我们使用github不也需要服务器吗？github服务器只是方便大家交流，并不是版本保存的必要设备，比如说marlin的github，其实哪怕服务器挂掉了，只要你电脑本地有clone过，你都可以在本地进行commit、branch等操作的。

#安装Git
直接到官网下载git：[https://git-scm.com/downloads](https://git-scm.com/downloads "Git")，安装非常简单。
#使用Git
安装git后，会有gui程序和命令行程序，两者都可以使用，但gui本质上也是执行命令行，以下都采用命令行来演示
##检出仓库


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

# 创建自己的GitHub

## 使用github的桌面工具