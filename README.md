# add new line to the README.md

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
