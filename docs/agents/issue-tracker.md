# 问题跟踪器：GitHub

本仓库的问题和规格说明记录在 GitHub Issues 中。所有相关操作使用 `gh` CLI。

## 约定

- 创建问题：`gh issue create --title "..." --body "..."`
- 查看问题：`gh issue view <number> --comments`
- 列出问题：`gh issue list --state open`
- 评论问题：`gh issue comment <number> --body "..."`
- 添加或移除标签：`gh issue edit <number> --add-label "..."` / `--remove-label "..."`
- 关闭问题：`gh issue close <number> --comment "..."`

在本仓库副本中执行命令时，根据 `git remote -v` 推断仓库；`gh` 会自动使用当前仓库。

## 将拉取请求作为分流入口

**PR 不是本仓库的请求入口。**

当技能要求“发布到问题跟踪器”时，创建 GitHub Issue。

## Wayfinder 约定

- **地图**：创建一个带有 `wayfinder:map` 标签的 Issue，正文包含 Notes、Decisions-so-far 和 Fog。
- **子任务**：使用 GitHub 子 Issue；如果仓库不支持，则在正文开头写 `Part of #<map>`，并使用 `wayfinder:research`、`wayfinder:prototype`、`wayfinder:grilling` 或 `wayfinder:task` 标签。
- **阻塞关系**：优先使用 GitHub 原生 Issue dependencies；不支持时，在子任务正文开头写 `Blocked by: #<n>, #<n>`。
- **认领**：使用 `gh issue edit <n> --add-assignee @me`。
- **解决**：先评论，再关闭 Issue，并将上下文指针补充到地图的 Decisions-so-far 中。
