# Git：diff，看改了什么

```bash
git diff                 # 工作区 vs 暂存区
git diff --staged        # 暂存区 vs 上次提交
git diff HEAD            # 工作区 vs 上次提交（全量）
git diff HEAD~1 HEAD     # 两次提交之间
git diff main...feature  # 两个分支的差异（三点是找共同祖先）
git diff --stat          # 只看改了哪些文件、各改几行
git diff --check         # 检查有没有行尾空格这类问题
```

- 提交前 `git diff --staged` 看一眼，确认没有把调试代码带进去。
- `--stat` 先看大局，再看具体 diff，别一上来就翻几百行。
- `git diff main...feature` 的三点和两点含义不一样，review 分支常用三点。
