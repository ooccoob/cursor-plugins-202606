---
name: arena
description: "针对同一任务并行生成 N 个候选，选出一个基础方案，把落选方案中最强的部分移植进去。用于 /arena、“把这件事放进竞技场”、“丢进竞技场”，或当对非平凡产物的一次尝试会锁定错误形态时。"
disable-model-invocation: true
---

# 竞技场

在启动任何东西之前，先开一个 todolist，每个阶段一条（Frame、Fan out、Cross-judge、Pick、Graft、Verify）。

## Phase A：界定

每个候选得到相同的 prompt，所以 prompt 就是契约。

1. 说明每个候选要产出的产物。
2. 推导评分标准，3-6 条具体可评分的准则，说明在*这个*任务上成功是什么样。它是 Phase D 中挑选者的工具。候选只看任务。
3. 从 `~/.cursor/rules/pstack-models.mdc` 的 `arena runners` 行挑选执行者，默认 `claude-fable-5-2-high`、`claude-opus-5-5-high-fast` 和 `gemini-4-neon-xhigh`。`auto` 或 `inherit-parent` 条目就是父模型，所以省略 `model` 并生成 `generalPurpose`。若 Task 工具拒绝某个 slug，用同家族最近的可用 slug 或去掉该席位，至少保留两个执行者，并说明。家族按前缀判定，最长匹配胜出：`claude-fable-*`、`claude-*` 和 `gemini-*`（先去掉开头的 `cursor-`）。其他 slug 的家族是第一个连字符之前的文本。多个设计方向时可多生成几个，当工作是生成密集而非判断敏感时，可重复同一模型。按 **poteto-mode** skill 的 Subagents 一节，为每个子代理的推理层级按任务选择。
4. 给每个候选各自的输出位置（尽量用 git worktree，否则 `/tmp/arena-<slug>/candidate-<n>/`），遵循 **separate-before-serializing-shared-state** 原则 skill。

## Phase B：分发

在一条消息中生成全部 N 个子代理，设 `run_in_background: true`，每个都带上任务、共享背景资料的路径、自己的输出路径，以及产出产物和一段简短理由的指令，理由需点名其考虑过的替代方案和否决了什么。

若某候选没有产出，用 N-1 继续并记录该掉队者。

## Phase C：交叉评判

Phase B 全部候选完成后，从 `~/.cursor/rules/pstack-models.mdc` 的 `arena cross-judge pool` 行生成一个只读评判者，默认 `claude-opus-5-5-high-fast`、`gemini-4-neon-xhigh`。评判者绝不能来自父模型的厂商，且 Fable 在该检查中算作 Claude，所以用其他厂商的第一个条目。`auto` 或 `inherit-parent` 条目就是父模型。若不知道父模型，用第一个真实 slug 并说明厂商检查未运行。若 Task 工具拒绝某个 slug，用同家族最近的可用 slug，再试下一个这样的条目，或跳过评判者，并说明。你在 Phase D 阅读的同时，评判者按路径标签为每个候选在每条评分准则上打分，并推荐一个基础方案。

## Phase D：选定基础方案

挑选前把每个候选从头到尾读完。按评分准则逐条打分，而不是凭整体感觉，并与交叉评判者对比（若 Phase C 运行了）。对基础方案的一致确认了选择。不一致意味着你们之一有偏见，或评分标准含糊。做决定前读双方的理由。

选出未来维护者最容易扩展且不破坏不变量的基础方案。当两个看起来并列时，优先边界更清晰或 API 更小的那个，遵循 Laziness Protocol。

## Phase E：移植

把每个落选候选再走一遍，找出值得移植进基础方案的部分，通常每个候选一两处，而不是大部分。按 **redesign-from-first-principles** 原则 skill，手工折入每处移植，使结果在单一心智模型下保持连贯。不要机械粘贴。

若候选收敛到同一形态，那是强一致。记录并交付该共识形态。无需移植。若它们严重分歧，说明 Phase A 界定不足。重新界定并重跑，而不是对分歧取平均。

## Phase F：验证

像对待任何其他输出那样验证合成后的产物，遵循 **prove-it-works** 原则 skill。若验证发现问题而竞技场漏掉了，要么 Phase A 错了（重新界定并重跑），要么某个候选发现了而你漏掉了移植（回到 Phase E）。不要掩盖它。

## 产出

一个合成产物，旁边附一份简短的综合说明，点名基础方案及理由、交叉评判者的裁决或 Phase C 跳过了评判者、每处移植及其来源候选、否决了什么及理由、任何收敛或掉队、以及验证结果。
