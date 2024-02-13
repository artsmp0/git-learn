# 学习 git

### 查看 git 提交历史

`git log -p -2`：

- `-p`: 它会显示每次提交所引入的差异
- `-2`: 限制条数

`git log --stat`:

- `--stat`: 简略显示文件变更

- `--pretty=oneline`: 一行显示

- `git log --pretty=format:"%h - %an, %ar : %s"`: 自定义输出格式

- `git log --pretty=format:"%h %s" --graph `: 图形化输出

- `git log --oneline --since=2.weeks`: 显示最近两周的提交

- `git log --oneline --since='2023-01-01' | wc -l`: 统计提交次数

- `--no-merges`: 隐藏合并提交

### 撤销操作

有时候我们提交完了才发现漏掉了几个文件没有添加，或者提交信息写错了。 此时，可以运行带有 --amend 选项的提交命令来重新提交。

```bash
git commit --amend
```

取消暂存文件。

```bash
git restore --staged file_name
```

还原某个文件的所有修改到上次 commit。

```bash
git checkout -- file_name
```

### 远程仓库的使用

`git remote -v`: 显示远程仓库的基本信息和 url

`git remote add <shortname> <url>`: 添加一个新的远程仓库

`git fetch fake`: 从远程仓库 fake 中拉取内容

运行 `git pull` 通常会从最初克隆的服务器上抓取数据并自动尝试合并到当前所在的分支

`git push <remote> <branch>`: 推送到指定远程仓库的指定分支

`git remote show origin`: 查看远程仓库的详细信息

`git remote rename <old_name> <new_name>`: 修改一个远程仓库的简写名

`git remote remove/rm <remote>`: 移除一个远程仓库

### 打标签

Git 支持两种标签：轻量标签（lightweight）与附注标签（annotated）

- 轻量标签很像一个不会改变的分支——它只是某个特定提交的引用
- 附注标签则包含一些信息：通过添加 `-a` 指令指名是附注标签，`-m` 指令添加备注

`git tag`: 列出已打标签
`git tag -a v1.0.0 -m "打标签 v1.0.0"`: 添加一个附注标签
`git show <tag_name>`: 显示一个标签的详情
`git push <remote> <tag_name>`: 在创建完标签后，必须显示推送标签到远程仓库上
`git push <remote> --tags`: 推送所有标签到远程仓库上
`git tag -d <tag_name>`: 删除本地标签，但不会删除远程仓库的标签
`git push <remote> :refs/tags/<tag_name>`: 删除本地标签后，同步到远程仓库
`git push origin --delete <tag_name>`: 同上
`git checkout <tag_name>`: 查看某标签的快照
`git checkout -b <branch_name> <tag_name>`: 对某个 tag 创建一个新分支，并修改内容

### 命令别名

- `git config --global alias.co checkout`
- `git config --global alias.unstage 'reset HEAD --'`
