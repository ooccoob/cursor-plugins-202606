### 开启 PR（Opening a PR）

在每个其他手册结束时被调用。

从基于主干的 git 工作树里干活，并把无关工作挡在外面。变基成小而可落地的提交。提交前对 diff 运行来自 `cursor-team-kit` 的 `/deslop`。

标题：`type(scope): subject`；当有某个真实符号承载这处改动时，就写出它。正文：40 行以内的一分钟简报，按顺序包含下列 `##` 标题，空的省略：`## Why`、`## What changed`、`## Scope`、`## Tradeoffs`（只写评审者本来会追问的被否决备选方案）、`## Blast Radius`、`## Verification`。

后续 PR 按基分支堆叠。以就绪状态开 PR，经由本轮的 PR 工具，参数 `draft: false`。没有该工具时，用不带 `--draft` 的 `gh pr create`，或在 Origin 的 CLI 能解析出仓库时用 `origin pr create --status open`。开启 PR 不会启动盯守。
