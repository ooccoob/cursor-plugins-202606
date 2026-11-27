---
name: show-me-your-work
description: "为长时间运行或无人值守的工作保留一条可复核的决策轨迹：一个 TSV 日志，每个决策一行（做什么、为什么、证据、结果）。默认本地保存；当评审者需要该轨迹才能信任结果时再提交。用于 /show-me-your-work、自主或多阶段运行，或人工离开后回来复核的工作。"
disable-model-invocation: true
---

# 展示你的工作

只保留一份权威日志。

## 格式

单个 TSV 文件，每个决策一行。单元格保持单行。证据是指针，不是散文。

复制 `references/decision-log-template.tsv`（表头行）以开始一份干净的日志。列：

- **ts。** ISO8601 时间戳。
- **phase。** 阶段或工作流。
- **decision。** 选了什么或做了什么，一行。
- **why。** 用平实的话说明理由。若某条原则驱动了它，就直说，不要用术语标签。
- **evidence。** 能证明它的链接或路径：commit SHA、PR 编号、`file:line`，或产物、trace、截图的路径。绝不要写成段落。
- **result。** 结果或谓词状态：`tests green`、`reverted`、`pixel-diff 0`、`INCONCLUSIVE`、`open`。

一个示例，用平实的话写，方便评审者一眼读完。

```
ts	phase	decision	why	evidence	result
2026-05-24T09:02:00Z	frame	counted the work first, about 100 components and roughly 75 hours	wanted to know the size before starting a long run	commit 3a9f1c2	found 5 things to sort out before starting
2026-05-24T09:40:00Z	harness	took screenshots of the old version before changing anything	so we can compare old against new and catch any visual change	scripts/snapshot.sh, baseline/	saved 120 reference screenshots
2026-05-24T11:15:00Z	widget	moved the widget styles over without changing how it looks	keep the change small and the result identical	commit 7c21e0a, pixel-diff 0	looks identical, tests pass
2026-05-24T12:30:00Z	widget	threw out a helper's work because its screenshots were blank	checked the real files instead of trusting its summary	worktree reset	reverted, tightened the instructions for next time
```

## 记录一行

每条记录都像向同事口述你做了什么那样写。用平实的话、具体的动作，不要 AI 腔或抽象术语（**unslop** skill 同样适用于日志文本）。

使用辅助脚本 `scripts/log.sh <logfile> <phase> <decision> <why> <evidence> <result>`。它写入 `ts`，首次使用时写表头，剔除多余的制表符/换行，并给任何以 `=`、`+`、`-` 或 `@` 开头的单元格加单引号前缀。用裸 `printf` 追加一行也可以，但若单元格来自生成内容或用户提供的文本，同样要注意这些字节。

记录决策点和检查点，而不是每个动作：选定的分叉、完成并验证过的单元、带触发条件的转向或回滚、暴露的阻塞、修复的关卡。循环运行时每次迭代一行。跳过琐碎和显而易见的内容。

一次运行是一个智能体对话，包括其后继轮次及其摘要。接手、替换智能体或新对话都开启新的一次运行。当一次运行追加到已有行的日志时，其第一行的 phase 为 `start`；在另一次运行的 `start` 行之后，它的第一行也是如此。因此后续轮次回到日志的运行，要先读日志最后几行，看是否已有其他运行写入过。`start` 行会标明它之前那些非本次运行写入的行的 `ts` 范围，其 evidence 指明本次运行（例如其 agent id）。phase `start` 不作他用。

## 存放位置

默认情况下日志是工作产物，不提交。放在工作目录的 `decisions.tsv`，或当多个工作并行时放在 `.audit/<task-slug>.tsv`，并排除在 git 之外。

仅当工作规模足够大、评审者需要该轨迹才能信任结果时才提交它。

## 规则

- 只追加。错误的判断用一行新记录取代它。绝不编辑或删除历史。
- 优先使用由已提交脚本产生的证据，而非手工的一次性产物（**encode-lessons-in-structure** 原则 skill）。

## 用对话记录审计日志

运行结束时、交回之前，检查日志是否如实。读取当前 workspace 的 `agent-transcripts/` 目录下本次运行的对话记录（系统提示会给出路径）。不要跨 `~/.cursor/projects/*/` 做 glob。那会读取无关的私人对话。把本次运行的行与实际发生的事逐条比对。本次运行的每一段行都始于本次运行的一条 `start` 行（若日志由本次运行创建，则始于第一行），止于另一次运行的下一条 `start` 行：

- 检查每一行都对应真实的决策或动作。
- 检查每一行的证据可解析，且能显示该行声称的内容。
- 影响工作但未记录的分叉、转向或放弃的方案是缺口。补上它。

修正日志，而不是改写故事。审计绝不编辑或删除任何行，哪怕是编造的。当某行既不记录真实决策也不记录真实动作，或其声称或证据有误时，追加一行取代它，写明实际发生的事和可解析的指针。此审计不检查本次运行各段之外的行。若本次运行的工作显示其中某行有误，像对待任何错误判断那样取代它。

## 跨模型复核轨迹

交回之前，用一个与执行工作者不同厂商模型的子代理。自我复核不能替代它。该子代理读取审计轨迹和本次运行的对话记录，标出用户应关注的点。不是重做工作，而是扫描次优或有风险之处。按 **poteto-mode** skill 的 Subagents 一节，为每个子代理的推理层级按任务选择。

- 证据薄弱或缺失的决策。
- 被跳过或在对话记录中无证据却声称已完成的验证步骤。
- 事后看有风险的选择（过早、范围蔓延、掩盖症状）。
- 用户随手一瞥容易漏掉的缺口。

任何产出了轨迹的运行的回复，都以“Attention”一节结尾。首行单独写出复核者模型（`reviewed by <model>`），然后列出每个标记，指向具体的行或时刻。“No flags”是有效值。模型名不是。

## 复核轨迹

从上到下读，跟随证据指针，抽查。GitHub 会把已提交的 TSV 渲染为表格。`column -s$'\t' -t decisions.tsv` 可在终端中渲染。

## 组合此 skill

其他 skill 把它们的审计轨迹交给这里，而不是自创一套。按名称引用它，让它掌握格式。不要复述各列。
