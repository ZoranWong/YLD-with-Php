# git
## git命令速查
* `git config --list` 查看已有配置信息
* `git config user.name` 查看用户名
* `git help <verb>` 使用帮助,若**< verb >**为**config**，则是学习**config**
* `git init` 初始化新仓库
* `git clone <url>` 克隆git某个项目
* `git status` 查看当前仓库文件变化
* `git diff ` 查看暂存前后变化
* `git diff --cached` 查看已经暂存起来的变化
* `git add <filename>` 添加某个文件到暂存区
* `git add .` 添加所有文件
* `git reset HEAD <filename>` 取消某个文件的暂存
* `git checkout --<filename>` 取消某个文件的全部修改  **慎用**
* `git commit -m "说明"` 提交到仓库
* `git commit -a -m "说明"` 跳过暂存区域，直接提交
* `git commit --amend`撤销最后一次提交
* `git remote` 列出每个远程库的简短名字
* `git remote -v` 显示对应的克隆地址
* `git remote add <remote-name> <url>`添加远程库，第一个参数命名，第二个地址
* `git fetch <remote-name>`从远程仓库抓取数据到本地
* `git push <remote-name> <branch-name>`将本地仓库数据推到远程仓库
* `git remote show <remote-name>`查看某个远程仓库的详细信息
* `git remote rename <old-name> <new-name>`修改某个远程仓库在本地的简称
* `git remote rm <remote-name>`移除某个远程仓库的链接
* `git branch branch-name`创建分支
* `git branch -vv` 查看本地分支与远程分支对应的关系
* `git branch -a` 查看远程所有分支
* `git checkout branch-name`切换分支
* `git checkout -b branch-name`创建并切换分支
* `git branch -d branch-name`删除分支
* `git merge branch-name`指定分支合并到当前分支
* `git branch --no-merged`查看尚未合并的分支
* `git branch`列出当前所有分支清单
* `git branch -v`查看各个分支的最后一次提交信息
* `git branch --merged`查看哪些分支已经并入当前分支
* `git rm <filename>`  删除文件
* `git rm --cached <filename>` 从git仓库中删除
* `git reflog`查看命令历史
* `git log` 查看提交历史
* `git log -p -2` －p选项展开每次提交的内容差异，用－2仅显示最新的两次更新
* `git log --stat` 仅显示简要的增改行数统计
* `git log --pretty=oneline`将每个提交放在一行显示
* `git log --pretty=short`
* `git log --pretty=full`
* `git log --pretty=fuller`
* `git log --pretty=format` 定制显示的记录格式



#### 手动合并

1、当两个分支修改了同一个文件后，在合并时，终端会出现以下类似输出

```
$ git merge iss53
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
```

注意： `Automatic merge failed; fix conflicts and then commit the result.`自动合并失败，需要手动修改文件，然后add、commit

2、产生冲突的文件形式大概如下：

```
<<<<<<< HEAD:index.html
<div id="footer">contact : email.support@github.com</div>
=======
<div id="footer">
 please contact us at support@github.com
</div>
>>>>>>> iss53:index.html

```

head部分是当前master分支代码，
`=======`上半部分，是master 分支代码；
下半部分是，iss53分支代码

可以在两部分进行取舍，或者手动合并这些内容

```
div id="footer">
please contact us at email.support@github.com
</div>
```

3、执行add、commit即可

 g