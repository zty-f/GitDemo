# GitDemo
git 命令测试使用项目
```go
// 上线合并分支流程

先new 一个branch（release-当前日期），然后把开发分支合并到这个branch

在把这个branch合并到master

打tag，去tag那里new一个即可，tag递增，message填写相关功能描述


//拉取对应分支
git pull origin 分支名称

//推送到远程分支
git push origin 分支名称

git checkout -b 分支名称
```


```go
git操作规范

修改新功能

1. git checkout master #切换到master分支
2. git pull  origin master #将master更新到最新状态
3. git checkout -b dev-分支名称  # 从最新master分支切出一个开发分支进行开发
4. 在3操作切出的分支进行功能开发·············
5. 功能完成后~
6. git checkout master #切换回到master分支
7. git pull  origin master #将master更新到最新状态（因为在开发过程中可能另外一个人已经将代码合并到master分支）
8. git checkout  dev分支 # 切换回到dev开发分支
9. git rebase master # 修改master基点
10.在从master重新创建新分支同步完成的功能
11. 然后在进行合并到master分支


// git 把一个分支的修改内容转移到master分支然后重新从master建立新分支
git stash

git checkout master

git pull origin master

git checkout -b hotfix-maxsendsize

git stash pop

git diff

git status

//  合并分支rebase
git checkout master 

git  pull

git checkout 开发分支

git rebase master

处理冲突 

git  push -f  #强制推送


// git合并多次commit操作

#### One
1.1 git add .  /   git  add 文件名

1.2. git commit --amend  "message" # 可以将本次提交合并到上一次提交

#### Two
2.1. git log # 查看提交记录

2.2. git rebase -i  HEAD~4 # 从HEAD版本开始往前数4个版本（根据需要变化起始值和结束值）

2.3. 进入vim编辑器过后修改需要合并的commit前缀，pick->s

例如：
pick commit1
s commit2
pick commit3
s commit4

上述修改即为把commit2和commit1合并，commit4和commit3合并，根据需要自己调整即可！

修改完成后保存退出

可能需要手动处理冲突（处理冲突后 git add .  &&   git rebase --continue）

上述流程完成后会进入commit信息修改，根据需要修改即可，然后保存退出

2.4. git push -f   /   git  push -f origin 远程分支   # 强制推送到远程分支
```

#### git 相关优质博文

[Git冲突解决](https://www.jianshu.com/p/33233174ef59)

[Git Rebase详解](https://blog.csdn.net/qq_30614345/article/details/130736404)