# Summary to Part2

### 使用 Git 管理修改和提交

#### 管理修改
git 的所有操作， 包括添加文件， 删除文件， 编辑文件等， 都算作一次修改，git 管理的并非文件，而是针对当前库中任意一次的修改。

#### 管理提交

git 使用 restore 和 reset 命令管理提交。

    - restore: 加上`--staged` 表示将文件从暂存区中撤出，即撤销 之前的 git add 行为。
    - reset: 主要用户撤销 commit 之后的行为
	- 加上`--soft HEAD~n` 表示仅仅撤销 commit 操作，但是不撤销 git add， 也就是不删除刚才对本地库的修改。
	- 加上`--hard HEAD~n` 表示不仅撤销 commit， 同时删除 commit 之前所有的修改。回到修改之前的第 n 个版本。

换句话说，对本地库做出的任何提交， 不论是 add 提交 还是 commit 提交， 都可以使用上面的命令加以回退。保证了可靠性。

### 其他命令简单使用

- 显示最近一次提交的内容: `git show`
- 清理无效的远程分支: `git remote prune origin`
