git版本控制器的基本应用

Git版本控制器是一个分布式版本控制器，在上次已经介绍过其更能与集中式版本控制器的区别，这次住要来介绍一下Git版本控制器的使用方法。

Git中，再多个人同时工作时，需要各自在自己的计算机上初始化Git库。git init
分区创建好后，查看工程状态。git status
接下来就可以在创建的Git库中创建文件了。然后可以使用　git status  命令来查看git仓库中的变化。git status 命令要经常运行，因为有些文件在变化时候容易忽略。
创建一个octocat.txt文件。此时创建的文件是未被Git跟踪的，因为他还没有被添加到本地的Git库中。现在要添加文件到暂存区，使得Git能够跟踪到Git库。使用命令　git add octocat.txt   将文件octocat.txt添加到Git。若是需要添加多个相同类型的文件，则可以使用通配符来一次性添加。　git add "*.txt"
添加文件到暂存区后，就可以用　git status　命令来跟踪文件了。
在文件存到git库之前，可以添加和删除暂存区中的文件。之后，提交暂存区文件的改变到本地的git库中，并且可以在命令里面添加该文件的详细描述信息。执行命令　git commit -m "这里是对文件变更的描述信息"
我们可以使用 git log　命令来查看我们所有的提交记录。
此时文件是在Git库中，要上传到远程仓库中，首先要添加远程仓库。使用代码　git remote add origin https:　　　后面是远程仓库的地址。
接下来就是将本地的文件推送到远程仓库中。使用命令　git push -u origin master   其中-u告诉Git记录远程仓库的参数，使之下次推送时候只需要使用命令　git push　即可推送。
此时，若其他人也进行该工程，就需要从远程Git库中拉取代码。使用命令　git pull origin master 　拉取代码。
做好修改后使用　git diff HEAD　　来活取最近一次提交的差异。查看暂存去文件的变化。
git add octofamily/octadag.txt 命令把octofamily/octodog.txt文件存放到暂存去中。也可以使用　　git reset octofamily/octodog.txt　　命令来删除octofamily/octodog.txt文件。使用　git checkout -- octocat.txt　　　命令可以恢复到最近一次提交的状态。
到此，Git的简单操作已经本完成。

Git还有一个比较好的功能就是分支了。分支就是在软件主线之外创建的另外一支。但是自己创建的分支别人是看不到的，这样，即使自己只完成了一个模块的一半提交上去之后，也不会影响到别人的正常工作。当自己的模块全部完成后，再将整个程序合并到主分支上即可。
创建分支　　git branch clean_up
切换分支　　git checkout clean_up
删除所有文件　　git rm '*.txt'
提交分支更改　　git commit -m "更改记录"
切换到主分支　　git checkout master
合并分支　　git merge clean_up
删除分支　　git branch -d clean_up
将所有的代码推送到远程仓库中　　git push
这就是分支的基本运行原理。

Git的基本应用已经列出来了，能够熟练地掌握，还需要自己的不断运用，亲身体会，多学多练，了解更多的分布式版本控制器功能。



