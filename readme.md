# git的范围
git config --local 
git config --global
git config --system

# git 当前文件夹的配置
git config --local user.name fanglin_yu
git config --local user.email fanglin_yu@163.com



# add 所有已经被git管理且有新的更改文件
git add -u 

# 简介查看当前分支log
git log --oneline 

# 简介查看当前分支最新4条log
git log --oneline -n4

# 简介查看所有分支log
git log --oneline --all

# 查看所有分支log的衍生版本历史
git log --oneline --all --graph


# 查看git的文件类型
git cat-file -t/-p
## -t 文件类型：tag,commit,tree和blob
## -p 如果 -t查询的文件类型为tag，则使用-p查询出来的是tag对应的类型的内容，包含object,type,tag name,tagger等
	  如果 -t查询的文件类型为commit，则使用-p查询出来的是本次提交对应的tree，本次提交的parent，本次提交的author及本次的committer
	  如果 -t查询的文件类型为tree，则使用-p查询出来的是文件列表
	  如果 -t查询的文件类型为blob，则使用-p查询出来的是文件内容
	  

# 分离头指针
1. git checkout xxxx (处于分离头指针的状态)
2. 修改文件，add到git并commit 得到一个uuid
3. 是否需要保存当前修改的文件到某个分支
	1. 是 -> git branch 分支名称 第2步得到的uuid，保存完成
	2. 否 -> 不用理会，git会当垃圾处理

# 删除分支 -d普通删除，-D强制删除
git branch -d/-D 分支名称

# 修改当前分支最近一次commit的message
git commit --amend

# 修改当前分支老旧的commit的message
1. git rebase -i 需要更改uuid的parent的uuid
2. 选择更改命令
	p,pick  使用commit
	r,reword  使用commit,但是编辑commit的message
	e,edit 使用commit,但是停下来修改
	s,squash 使用commit,但是合并到其他commit中
	
# 查看暂存区和HEAD文件差异
git diff --cached

# 查看工作和暂存区文件差异
git diff

# 查看工作和暂存区指定文件差异
git diff -- 文件位置（注意：--和文件位置之间有空格）

# 暂存区恢复成HEAD
git reset HEAD 

# 暂存区恢复成HEAD  指定文件
git reset HEAD -- filename

# 工作区的文件恢复和暂存区一致
git checkout -- filename 

## 暂存区变化 reset

## 工作区变化 checkout


# 消除最近几次commit 危险！！！
git reset --hard uuid

# 查看两个分支之间的差异
git diff 分支1/commit2 分支2/commit2  -- filename

# 删除文件
git rm filename

# 暂存文件
git statsh 
# 查看暂存文件
git stash list

# 取出暂存文件
## 1. git stash apply  恢复文件到工作区，保留文件在 stash list
## 2. git stash pop    恢复文件到工作区，删除文件