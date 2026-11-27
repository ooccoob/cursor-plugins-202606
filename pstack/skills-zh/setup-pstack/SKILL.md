---
name: setup-pstack
description: 配置 pstack 每个角色使用哪个模型以及推理预算。检测你可用的模型，并写入一条始终生效的规则来覆盖 skill 默认值。用于 /setup-pstack、“配置 pstack 模型”、“pstack 预算”，或更改 pstack 的模型选择。
---

# 配置 pstack

写入 `~/.cursor/rules/pstack-models.mdc`，这是一条始终生效的规则，按角色设定 pstack 的模型。

## 步骤

### 1. 检测可用模型

枚举本会话中可以传给 `Task` 子代理的模型 slug。这是可靠的来源。如果 Cursor 还暴露了 models API 或 CLI 能列出用户已获授权的模型，优先用它以保证完整。如果检测不到任何模型，请用户粘贴其有权访问的 slug。绝不要写入你未确认可用的真实 slug。别名 `inherit-parent` 和 `auto` 始终有效，即使它们不是被检测到的 slug。

### 2. 加载当前状态

默认的角色到模型映射就是下面第 5 步所示的规则形态。若 `~/.cursor/rules/pstack-models.mdc` 已存在，读取它，把它的 `# budget` 行和各角色值当作当前选择。否则从这些默认值开始。角色不在第 5 步中的行（例如 `hardest tasks`、`architect runners`、`reflect tooling` 或 `why investigators`）来自已退役的角色，删除它。

旧默认值曾把另一个 Gemini 模型、随后是 `gemini-4-neon-high`，放在评审席位上。因此任何规则中，面板角色（`arena runners`、`arena cross-judge pool`、`interrogate reviewers`）里的 `gemini-4-neon-high` 条目，或除 `gemini-4-neon-*` 之外的 `gemini-4-*` 条目，都是旧默认值。每一条都改为 `gemini-4-neon-xhigh`。其他层级的 Gemini 4 Neon 条目是用户的选择，保留。告诉用户你替换了哪些条目。

没有 `# defaults: 3` 行的规则来自更早的配置。那种配置为每个角色都写了一行，所以其中一些值是旧默认值而非用户选择。在第 3 步之前，替换这些值：

- `arena cross-judge pool` 列表恰好由一个 `claude-fable-*` 条目、一个 `claude-opus-*` 条目和一个 `gemini-*` 条目组成（顺序任意）时，改用该角色在第 5 步的列表。Fable 与 Opus 属同一厂商，所以 Fable 条目只能评判 Opus 条目也能评判的地方。
- `# budget: unlimited` 行改为 `large`，因为没有角色在 `xhigh` 之上运行。
- 如果该规则也没有 `# defaults: 2` 行，那么匹配 `grok-*` 的 slug 就是旧 slug。`feature, refactoring`、`bug-fix`、`perf-issue`、`hillclimb` 或 `swarm workers` 中的旧 slug 改用该角色第 5 步的默认值。在面板角色（`arena runners`、`arena cross-judge pool`、`interrogate reviewers`）中，恰好由一个 `claude-opus-*` 条目和一个旧 slug 组成的列表（顺序任意）改用该角色第 5 步的列表。在任何其他列表中，每个旧 slug 都改为 `claude-opus-5-5-high-fast`。

其他所有值都是用户的选择，保留，包括任何其他角色中的旧 slug 以及所有 `inherit-parent` 或 `auto` 值。告诉用户你替换了哪些值。

### 3. 预算、映射与确认

**（a）询问预算。** 优先用 AskQuestion 而非自由文本。给出这三个选项，标签必须与下面完全一致；若规则中记录了当前预算，就一并说明。没有规则时，说明 `large` 与 skill 默认值一致。

- `large — xhigh reasoning`
- `medium — high reasoning`
- `small — medium reasoning`

**（b）应用它。** 从 skill 默认值构建工作表，重跑时保留你按家族、列表或别名（`inherit-parent`、`auto`）改动过的角色。家族由 **arena** skill 的 Phase A 定义，所以 Fable 自成一个家族。每个角色有一个目标力度，即其默认力度按预算移动后的值。`large` 保持不变，`medium` 降一档，`small` 降两档，阶梯为 `xhigh` > `high` > `medium` > `low`。没有角色在 `xhigh` 之上运行，位于阶梯底部的目标保持不变。大多数默认值在 `xhigh`，每个预算标签都点明这些值落在哪里。把角色中每个真实 slug 的力度词元（含面板条目）设为该角色的目标。力度词元是最后一个词元，或结尾 `fast` 之前的那个。若结果不是被检测到的 slug，改用同家族中力度最高且不高于目标的已检测 slug；否则标记该角色需要选择。`inherit-parent` 和 `auto` 不变。因此 `medium` 把 `claude-opus-5-5-xhigh-fast` 变成 `claude-opus-5-5-high-fast`，把 `claude-opus-5-5-high-fast` 变成 `claude-opus-5-5-medium-fast`；`small` 把它们变成 `claude-opus-5-5-medium-fast` 和 `claude-opus-5-5-low-fast`。Opus 5.5 始终运行其 `-fast` slug，所以每个 Opus 5.5 值都以 `-fast` 结尾。Fable 5.2 和 Gemini 没有 fast slug，绝不要写。Gemini 4 Neon 的 slug 从 `low` 到 `xhigh`，没有 `max` 或 `fast` slug，所以它的席位运行在 `gemini-4-neon-xhigh`，即其最高 slug。面板角色中的 Gemini 4 Neon 条目取它自己的目标，即 `xhigh` 按预算移动后的值，所以 `large` 保留 `gemini-4-neon-xhigh`，`medium` 写 `gemini-4-neon-high`，`small` 写 `gemini-4-neon-medium`。

**（c）展示角色并确认。** 展示每个角色及其模型，把不在检测集合中的真实 slug 标记为需要选择。同时列出第 2 步删除的每一行。询问是原样接受还是修改特定角色，选项为检测到的模型（`xhigh` 及以下）加上 `inherit-parent` 和 `auto`（两者都表示：该角色运行在父对话模型上，Auto 用户因此仍留在 Auto）。优先用 AskQuestion 而非自由文本。面板角色（arena runners、interrogate reviewers）的值是列表，每个条目运行一个子代理（含别名条目），所以列表长度决定数量。`arena cross-judge pool` 也是列表，但 Arena 只运行一个评判者。它只尝试与父模型不同厂商的值，按列表顺序，因此请按偏好排序。Fable 与其他 Claude 模型属同一厂商。`inherit-parent` 或 `auto` 值从不担任评判。`swarm workers` 是每个 worker 的默认模型，除非某次竞赛或比较为某一臂另行指定模型。

### 4. 校验

写入的每个真实 slug 都必须在检测集合中且为 `xhigh` 或以下。`inherit-parent` 和 `auto` 始终通过。若选定的真实 slug 不可用，停止并重新询问。

### 5. 写入规则

写入 `~/.cursor/rules/pstack-models.mdc`，包含 `alwaysApply: true`、`# defaults: 3` 行、带所选标签及该标签所指力度的 `# budget` 行，以及每个角色一行，标签与 poteto-mode 使用的相同。整体覆盖文件，使重跑保持幂等。形态：

```
---
description: pstack per-role model choices (overrides skill defaults)
alwaysApply: true
---
# pstack 模型配置。每个角色一行。删除某行即回退到 skill 默认值。
# 以 `inherit-parent` 或 `auto` 作为值：该角色运行在父对话模型上（省略 Task 的 `model` 并 spawn `generalPurpose`）。面板列表中的别名条目仍计入其扇出数量。
# defaults: 3
# budget: large (xhigh)
feature, refactoring: claude-opus-5-5-xhigh-fast
bug-fix: claude-opus-5-5-xhigh-fast
perf-issue: claude-opus-5-5-xhigh-fast
hillclimb: claude-opus-5-5-xhigh-fast
judgment and prose: claude-opus-5-5-xhigh-fast
arena runners: claude-fable-5-2-high, claude-opus-5-5-high-fast, gemini-4-neon-xhigh
arena cross-judge pool: claude-opus-5-5-high-fast, gemini-4-neon-xhigh
swarm workers: claude-opus-5-5-high-fast
interrogate reviewers: claude-fable-5-2-high, claude-opus-5-5-high-fast, gemini-4-neon-xhigh
```

### 6. 确认

告诉用户规则已写入，且对新会话生效。重跑此 skill 会更新它。

### 7. 提供一个验证 skill（可选）

检查项目是否有办法驱动真实应用以取得证明（`verify-*` skill，或已有的 harness）。若没有，提议一次：“想要一个项目本地的验证 skill，让智能体能像用户那样驱动应用并证明改动有效吗？我可以用 /create-verification-skill 生成一个。”若同意，调用 `/create-verification-skill`（在 pstack 安装的任何位置解析：workspace、user 或 plugin）。若拒绝，继续推进，不再劝说。

### 8. 提供一个形式化验证 skill（可选）

检查项目是否已有形式化验证 skill（针对代码运行模型检查器、证明或其他验证器的项目 skill）。若没有，提议一次：“想要一个形式化验证 skill，让智能体能证明代码的某个关键性质在范围内每种情况下都成立，而不只是测试能覆盖的情况吗？我可以用 /create-formal-verification-skill 生成一个。”若同意，调用 `/create-formal-verification-skill`（解析位置同上）。若拒绝，继续推进，不再劝说。
