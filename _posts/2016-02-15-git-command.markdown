---
layout: post
title: Git常用命令备忘
date: 2016-02-15 15:32:24.000000000 +09:00
---

克隆远程版本库：
```shell
git clone git@git.example.com:tech/front.git
```

克隆远程版本库的一个分支（develop）：
```shell
git clone -b develop git@git.example.com:tech/front.git
```



查看文件状态：
```shell
git status
```

添加修改的文件到暂存区：
```shell
git add [filename / dir / -A]
```

提交修改：
```shell
git commit -m “这里简单写一些修改了什么”
```

拉取最新的远程仓库数据：
```shell
git pull
```

推送提交的修改到远程服务器：
```shell
git push
```




从当前的跟踪列表移除文件，并完全删除：
```shell
git rm filename.txt
```

仅在暂存区删除，保留文件在当前目录，不再跟踪：
```shell
git rm -cached filename.txt
```

重命名文件：
```shell
git mv filename1.txt  filename2.txt
```



查看仓库分支：
```shell
git branch -a
```

切换到develop分支：
```shell
git checkout develop
```

检出本地被删除的文件：
```shell
git checkout filename.txt
```

查看提交的历史记录（日志）：
```shell
git log
```

查看main.js在哪些版本中有变化：
```shell
git log –pretty=[oneline / short / full / fuller / format:] main.js
```

查看该版本有哪些变化：
```shell
git show a1ee15b8d6eed61a63e172c5d09b4679892c4796
```

恢复某一版本：
```shell
git reset [file / dir / tagName] version
```



查看储藏室列表：
```shell
git stash list
```

加入储藏室：
```shell
git stash
```

从储藏室弹出最后一个版本：
```shell
git stash pop
```

没有自动合并，使用git pull提示如下错误的解决方式：
```
haleywang@mos:~/Document/frant$ git pull
You have not concluded your merge (MERGE_HEAD exists).
Please, commit your changes before you can merge.
```

1. 保留本地修改：
```shell
git merge –abort
git reset –merge
```
合并后记得一定要提交这个本地的合并
然后在获取线上仓库
```shell
git pull
```

2. 下载远程代码版本，抛弃本地的修改
不建议这样做，但是如果你本地修改不大，或者自己有一份备份留存，可以直接用线上最新版本覆盖到本地
```shell
git fetch –all
git reset –hard origin/master
git fetch
```


显示git的地址
```shell
git remote -v
```

恢复版本
```shell
git reset –hard HEAD
```

删除本地分支
```shell
git branch -d master
```

删除远程分支
```shell
git push origin :master
```

创建本地分支
```shell
git checkout -b master
```

将本地分支推到远程
```shell
git push origin master:master
```


切换并创建一个新分支hotfix-1.2.1  （基于master分支）
```shell
git checkout -b hotfix-1.2.1 master
```
