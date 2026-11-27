---
name: poteto-help
description: 引导用户完成 pstack 的初始设置、使用 /poteto-mode，并为任务挑选合适的 Skill、手册或原则。输入 /poteto-help 并附上问题即可。
disable-model-invocation: true
---

# Poteto 帮助

回答用户关于 pstack 的问题，交给他们一段可以直接发送的提示词，并附上答案所出自的文件链接。对于帮助类问题，不要直接开始干活。用户问的是"怎么做"，而一次 pstack 运行会消耗真实的 token，所以把提示词交给他们自己发送。

提出工作要求（例如"用 pstack 修这个缺陷"）的消息不是帮助类问题。阅读 [`poteto-mode`](../poteto-mode/SKILL.md)，在其指导下完成工作，并顺带提一句：把它设为 Custom Mode 就能让它一直生效。

本文件把问题映射到存放答案的 Skill 与指南页面。细节归那些文件所有。引用之前先读你要路由到的文件，当它与本映射冲突时以它为准。这里的链接指向已安装的插件内部，用户可能打不开，所以给用户文件的公开副本：`https://github.com/cursor/plugins/blob/main/pstack/` 加上它的路径。

## 弄清他们的需求

从消息和对话中推断需求。点明了场景的（例如"哪个 Skill 会评审 PR？"），直接跳到对应小节。如果需求仍不明确，就问一个多选题，选项如下，然后只回答他们选中的那一节：

- 完成初始设置
- 用 `/poteto-mode` 开始一个任务
- 为某个场景挑选 Skill
- 修复出错的运行
- 让 pstack 成为我自己的

检查那些会改变答案的状态，并且只在它确实影响答案时提及：

- 没有 `~/.cursor/rules/pstack-models.mdc`，说明该用户还没运行过 `/setup-pstack`，因此每个角色都使用默认模型。
- 项目里没有 `verify-*` Skill 或其他应用测试装置，说明智能体没有脚本化的方式来驱动应用。当问题涉及证明某处变更确实生效时，提及 `/create-verification-skill`。
- 项目里没有形式化验证 Skill，说明除测试能触及的范围之外没有其他性质被检查。当问题涉及竞态、不变量或其他测试很少命中的情形时，提及 `/create-formal-verification-skill`。若已存在一个，而它覆盖的代码在它记录为最后同步的提交之后发生了变化，那么当问题涉及那段代码时，提及 `/maintain-formal-verification-skill`。

当模型规则缺失且这件事确实重要时，询问用户是否现在就为每个角色挑选模型与推理预算。以下情况它很重要：用户是新手、问题涉及设置或成本，或答案取决于运行哪些模型。每个对话最多问一次。如果需求也不明确，就把两个问题一起问。给出两个选项：

- 现在：给他们 `/setup-pstack` 让他们输入，同时回答他们的问题。
- 稍后：回答他们的问题，并加一句说明：在他们运行 `/setup-pstack` 之前，每个角色都保持默认模型。

## 完成初始设置

1. 在对话中用 `/add-plugin pstack` 安装，或从侧边栏的 Customize 安装。
2. 运行 [`/setup-pstack`](../setup-pstack/SKILL.md)。它会询问推理预算，为每个角色映射一个模型，并写入一条规则。该规则对新对话生效。随后它会各提供一次机会，为项目生成一个验证 Skill 和一个形式化验证 Skill，除非项目里已经有了。
3. 用 `/poteto-mode`、一个目标，以及一个能通过或失败的检查，开始一个真实任务。

安装本身不会改变任何东西，直到用户调用某个 Skill。只有 `/setup-pstack` 会从用户的话里加载。[README](../../README.md) 与[指南第 1 页](../../docs/guide/01-setup.md)有细节。可以提议与他们一起推敲第一条提示词，做法见 [`references/prompting.md`](references/prompting.md)。

如果担心成本，就说明 token 花在哪里，以及如何少花一些。pstack 会把额外 token 花在子代理和评审小组上。重新运行 `/setup-pstack`，选一个更小的预算或更便宜的模型。把某个角色设为 `auto` 或 `inherit-parent`，它就跑在对话所用的模型上；当对话跑在 Auto 或更便宜的模型上时，这样能省 token。评审小组列表越短，跑的越少子代理，列表里每一项对应一个。把 `/poteto-mode` 留给需要严谨性的工作。

pstack 是为 Cursor 构建的，也能装进 Claude Code：先 `/plugin marketplace add cursor/plugins`，再 `/plugin install pstack@cursor-plugins`。在那里，每个命令都要加 `pstack:` 前缀，例如 `/pstack:poteto-mode`。[Claude Code 适配层](../../docs/harness/claude-code.md)负责映射 Cursor 的名字，而需要 Cursor 专有特性的步骤（例如 Bugbot 或 Automations）会被跳过并附一行说明。

其他工具也能读取这些 Skill，因为它们使用 Agent Skills 格式。但大多数工作流 Skill（包括 `/poteto-mode`、`/how` 和 `/teach`）会创建 Cursor 子代理，其中一些还按角色指定模型，而 Custom Mode 与 `/loop` 都是 Cursor 的特性，所以这些部分在那里可能无法工作。

## 用 `/poteto-mode` 开始一个任务

`/poteto-mode` 会把任务匹配到一本手册，把手册的步骤复制进待办列表，并按步骤需要运行其他 Skill。好的提示词会说明目标以及如何判断已经完成。它不罗列 Skill，因为手写的顺序往往会漏掉或打乱手册本会保留的步骤。在帮他们推敲提示词之前，先读 [`references/prompting.md`](references/prompting.md)。[指南第 2 页](../../docs/guide/02-poteto-mode.md)有示例。

`/poteto-mode` 是否会持续生效，取决于用户如何启动它：

- 在 `/poteto-mode` 上按 Enter，会把该 Skill 附加到一条消息上。随着对话推进，它会淡出。
- 在 Mac 上按 Option+Enter、在 Windows 上按 Alt+Enter，或在 Skill 条目中选择 Use as Mode，会把它变成 Custom Mode。它会在每一轮都留在上下文中，直到用户退出该模式，同时它会避开随意的闲聊轮次。
- Cursor 的文档把 Custom Mode 列在 Agents Window 和 CLI 中。其他场合下，每个新任务都用 `/poteto-mode` 开始。

出现这个话头时，链接到 [Cursor 的 Skill 文档](https://cursor.com/docs/skills)。在对话中途说"新任务"，会让该模式去匹配一本全新的手册。`/poteto-mode` 已经使用 `poteto-agent` 来运行其手册步骤所创建的子代理。若想让自己创建的子代理也有同样的风格，就用 `subagent_type: "poteto-agent"` 创建它。

## 挑选 Skill

默认答案是 `/poteto-mode`，它会在步骤需要时运行大多数其他 Skill。当用户想要的比手册给的更多或更少时，直接点名某个 Skill。推荐之前先读该 Skill，并给出一个示例提示词。

| 用户想要 | Skill |
|---|---|
| 以严谨的方式完成任何非平凡任务 | [`/poteto-mode`](../poteto-mode/SKILL.md) |
| 在开工前确认智能体已理解其目标与问题 | [`/in-your-own-words`](../in-your-own-words/SKILL.md) |
| 在发送前把提示词改得更有深度而非更长：顶尖专家会补充什么、他们的原始素材与方法，以及一次外部校验。它只返回提示词，不执行任务 | [`/sharpen`](../sharpen/SKILL.md) |
| 学会描述自己正在构建之物的专业词汇（包括借用自邻近领域的词），每个引用的来源都经过核实，并用这些词重写自己的描述 | [`/reframe`](../reframe/SKILL.md) |
| 了解代码当前如何运作，或新代码应该放在哪里 | [`/how`](../how/SKILL.md) |
| 了解代码为何是这个样子，或某个数字从何而来 | [`/why`](../why/SKILL.md) |
| 用平实的话理解一处变更或子系统 | [`/teach`](../teach/SKILL.md) |
| 补齐自己在某个主题上的近期工作进展 | [`/recall`](../recall/SKILL.md) |
| 用平实的语言和少量图示，补齐本对话自他们上条消息以来的变化，并列出每一项在等他们处理的事，且仅凭这条回复就能做出决定 | [`/ketchup`](../ketchup/SKILL.md) |
| 像 `/ketchup` 一样补齐进展，但以带字幕的短幻灯片视频呈现，把待决策事项以文字列在下方 | [`/ketchup-video`](../ketchup-video/SKILL.md) |
| 了解一处小改动可能在自身之外破坏什么 | [`/blast-radius`](../blast-radius/SKILL.md) |
| 在写跨函数边界的代码之前，先确定类型与模块形态 | [`/architect`](../architect/SKILL.md) |
| 针对同一份任务说明得到多个尝试，并合并为最好的一个 | [`/arena`](../arena/SKILL.md) |
| 以云智能体的形式对切片并行检查，或让多个 worker 竞速 | [`/swarm`](../swarm/SKILL.md) |
| 让不同模型审查一处 diff 并尝试攻破它 | [`/interrogate`](../interrogate/SKILL.md) |
| 当存在低成本的本地测试时，以测试先行方式修复缺陷 | [`/tdd`](../tdd/SKILL.md) |
| 对 `.ts` 或 `.tsx` 工作应用 TypeScript 规则 | [`/typescript-best-practices`](../typescript-best-practices/SKILL.md) |
| 在评审前清除注释，并使用没有写过这些注释的评审者 | [`/no-comments`](../no-comments/SKILL.md) |
| 清除文字中的 AI 痕迹 | [`/unslop`](../unslop/SKILL.md) |
| 按标准撰写文档、RFC、README、PR 描述或提交信息 | [`/technical-writing`](../technical-writing/SKILL.md) |
| 用平实的话再听一遍上一条回复 | [`/bro`](../bro/SKILL.md) |
| 给智能体一套脚本化的方式来驱动应用并证明行为 | [`/create-verification-skill`](../create-verification-skill/SKILL.md) |
| 让验证 Skill 及其功能清单重新与应用保持一致 | [`/maintain-verification-skill`](../maintain-verification-skill/SKILL.md) |
| 对竞态、不变量或测试很少触及的其他性质做形式化验证 | [`/create-formal-verification-skill`](../create-formal-verification-skill/SKILL.md) |
| 在其覆盖的代码发生变化后让形式化验证重新对齐，并判断失败是漂移还是缺陷 | [`/maintain-formal-verification-skill`](../maintain-formal-verification-skill/SKILL.md) |
| 以经 TLA+ 模型校验的图表，向 PM 或设计师展示用户所见，并给出到达每个违规状态的最短路径 | [`/statechart`](../statechart/SKILL.md) |
| 在汇报或依据某个性能数字行动之前先做核验 | [`/benchmark-checklist`](../benchmark-checklist/SKILL.md) |
| 执行大型或跨领域的变更，或执行一项离开后仍需复核的变更 | [`/figure-it-out`](../figure-it-out/SKILL.md) |
| 在运行过程中保持决策日志，并在事后复核 | [`/show-me-your-work`](../show-me-your-work/SKILL.md) |
| 为每个角色选择模型与推理预算 | [`/setup-pstack`](../setup-pstack/SKILL.md) |
| 把自己的工作习惯变成一个个人模式 Skill | [`/automate-me`](../automate-me/SKILL.md) |
| 把一项已完成任务带来的经验转化为 Skill 修改 | [`/reflect`](../reflect/SKILL.md) |
| 阻止智能体在此仓库中重复同样的错误 | [`/correct`](../correct/SKILL.md) |
| 构建一个页面，其按钮可通过 webhook 唤醒 Grok Bot | [`/make-bot-ui`](../make-bot-ui/SKILL.md) |
| 找到 pstack 的用法 | `/poteto-help` |

如果本文件旁边的某个 Skill 目录未出现在表格中，读它的 frontmatter 并按 description 路由。`principle-*` 目录见下面的原则小节。

易混淆的情形：

- `/how` 解释代码做什么。`/why` 解释原因。`/teach` 运行其中之一或两者，并平实地解释结果。
- `/arena` 给每个 worker 同一份任务说明，并合并其中最好的部分。`/swarm` 把工作切成切片或一场竞速，并返回一份报告。
- `/interrogate` 评审 diff。`/blast-radius` 在 diff 之外寻找破坏，并证明那件让变更安全的关键事实。
- `/recall` 跨近期对话重建上下文。`/ketchup` 只覆盖本对话自用户上条消息以来的部分。恢复某个特定对话或分支属于 Session pickup 手册。
- `/figure-it-out` 设计一次严谨的运行。Autonomous run 手册把一个任务推进到完成条件。

不在 pstack 中：

- `/deslop`、`control-cli` 和 `control-ui` 由 `cursor-team-kit` 插件提供。
- `/loop` 和 `/create-skill` 是 Cursor 内置功能。
- pstack 没有 `/orchestrate` Skill。如果斜杠菜单里出现 `/orchestrate`，那是别的插件提供的。

## 手册与原则

手册是 `/poteto-mode` 内部的步骤列表，不是 Skill，因此没有斜杠命令。在 `/poteto-mode` 中，描述任务即可挑中一本；下面这些说法可直接点名：

- "babysit this pr" 或 "check on pr 123" 运行 Babysit。它把 PR 推进到可合并就绪，并在那里停下。除非用户要求合并、落地或发布，否则它不会合并。
- "land the stack" 运行 Shipping。
- "take over this branch" 运行 Session pickup。
- "pause safely" 运行 Pause safely。
- "full autopilot on this queue" 运行 Autopilot-full。"autopilot, don't merge" 运行 Autopilot-stack。
- "run the eval playbook" 运行 Eval。

不带 `/poteto-mode` 时，像 "babysit this pr" 这样的说法可能会启动 Cursor 自己的同功能 Skill。[`poteto-mode`](../poteto-mode/SKILL.md) 的 Playbooks 小节列出了每一本手册。[指南第 6 页](../../docs/guide/06-verify-and-ship.md)涵盖开启、babysit 与落地 PR。

pstack 没有规划 Skill。Cursor 的 Plan Mode 可与它并行使用。对于跨阶段或堆叠 PR 的工作，向 `/poteto-mode` 要一份计划会运行 [Multi-phase plan 手册](../poteto-mode/playbooks/multi-phase-plan.md)，它只写计划、不实现。对于设计问题，Prototype 手册或 `/architect` 会先在代码里把它定下来。

原则是单条规则的 Skill，`/poteto-mode` 会读取它们并在回复中引用。用户很少主动调用其中某一条。他们改用名字来引导，例如"apply prove it works. show me the real output."。输入 `/principle-<name>` 仍可按需加载一条。[指南第 8 页](../../docs/guide/08-principles.md)列出了它们。

## 修复出错的运行

| 现象 | 修复 |
|---|---|
| 几轮之后模式不再生效 | 它是用 Enter 启动的。改为以 Custom Mode 启动，或每个任务都用 `/poteto-mode` 开始。 |
| 一个问题被当成了上个任务的下一步 | 说"新任务"，或说明这一轮不需要该模式。 |
| 新的模型选择没有效果 | `/setup-pstack` 写下的规则对新对话生效。开一个新对话。 |
| 运行成本高于预期 | 见"完成初始设置"下的成本段落。 |
| 某个 Skill 没有自行加载 | 只有 `/setup-pstack` 会从用户的话里加载。其他 Skill 在用户输入时、或由 `/poteto-mode` 运行时加载，而它并不会运行每一个 Skill。 |
| 并行智能体互相覆盖 | 给每个智能体各自的工作树，或把它们作为云智能体运行，各自获得独立的机器。 |
| 一次过夜运行有动作却什么都没完成 | `/loop` 需要一个能通过或失败的检查，而不是一个时长。见[指南第 7 页](../../docs/guide/07-overnight.md)。 |
| 回复凭一次绿色构建就宣称成功 | 索要真实的命令、流程、存储值或性能剖析。那就是 prove-it-works 原则。 |

对于跑偏的运行，[`references/prompting.md`](references/prompting.md) 有一行式的引导语。[指南第 10 页](../../docs/guide/10-recipes-and-pitfalls.md)有更多陷阱与值得照抄的配方。

## 让 pstack 成为我自己的

- [`/automate-me`](../automate-me/SKILL.md) 从用户自己的历史中起草一个个人模式 Skill，与 `/poteto-mode` 搭配使用。
- 一次会话之后用 [`/reflect`](../reflect/SKILL.md)，把其中的经验转化为用户认可的 Skill 修改。
- `/poteto-mode write a skill for <workflow>` 运行编写手册。eval 手册会以盲测方式检验 Skill 变更。
- 修一个有问题的 Skill 要用它自己的 PR，而不是在它出问题的那个功能工作里顺手改。

[指南第 9 页](../../docs/guide/09-make-it-yours.md)涵盖上述每一项。

## 回复

先给答案。最多给一个放在代码块里的示例提示词，若有合适的就从 [`references/recipes.md`](references/recipes.md) 改编，然后给出指向该文件的链接。除非用户要的是完整地图，否则保持简短。
