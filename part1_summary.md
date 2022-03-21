# Summary for Part1

### git 提交相关的操作

- Using `-p` flas after `git add`:
> Begin an interactive staging session that lets you choose portions of a change to add.
- 使用`git add -p` 之后, 会开启一个交互式的 staging 会话, 该会话会逐个列出当前的修改, 并询问是否要将修改添加进 stage 中。在会话给出的选项中, y 表示提交本次修改, n 表示不提交本次修改, s 表示切割此次修改(在s 被给出的前提下)。
- s 给出的条件是 git 会检测当前的修改中是否存在可以`切割成更小hunk` 的修改。如果存在, git则会在询问时列出s 选项。如果 git 未检测到相关修改, 则看不到 s 选项。
	- 能够切分修改(给出 s 参数的条件): 当有修改发生在一段未修改内容的前后,git 会将修改从未修改的部分切割成更小的 hunk。
	```
		修改 1
		修改 2
		original content
		修改 3
	```
此时， git add -p 之后， 会给出 s 选项， 当输入 s 之后， git 会从 original content 开始， 将本次的修改分割为 2 次小的修改，逐个询问。当然，如果修改发生在多个原始内容前后，也会逐个切分并询问。 
