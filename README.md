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
