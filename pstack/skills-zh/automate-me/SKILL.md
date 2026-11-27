---
name: automate-me
description: "用于“automate me”“创建/更新/刷新我的 -mode skill”“把我的偏好或工作风格转成/固化成 skill”，或希望智能体按用户的工作方式行事时。通过 create-skill + unslop 起草或修订个人 -mode skill，可选择从近期对话记录中拉取新证据。"
disable-model-invocation: true
---

# 自动化我

一条引导式流程，把用户的工作惯例转成智能体会遵循的 skill。输出是一个为其量身定制的 `-mode` skill（例如 `jay-mode`、`priya-mode`）。

此 skill 编排另外三个：一次内联挖掘（见第 1 步）、Cursor 内置的 `create-skill`（撰写）以及 **unslop** skill（行文纪律）。它只负责编排顺序，不替代它们。

## 流程

### 0. 检查是否已有 skill

递归查找匹配用户 handle 的 `.cursor/skills/**/*-mode/SKILL.md` 和 `~/.cursor/skills/*-mode/SKILL.md`。mode skill 可以放在个人分类目录中（`.cursor/skills/<handle>/`），不只在顶层。若已存在，用 `AskQuestion` 确认意图（除非用户已说“更新我的 skill”之类的话）：

- 更新已有的 skill（重复运行时的默认选项）
- 从头开始（少见，执行前先问原因）

更新模式会改变后续流程：
- 第 1 步只挖掘该 skill 上次编辑以来的历史（`git log -1 --format=%cI <path>`）。
- 第 2 步询问哪里变了或缺了什么，而不是从零问要捕获什么。
- 第 4 步就地编辑已有文件。保留用户未否定的章节。用新证据修订章节。只为真正新的规则新增章节。

### 1. 挖掘其历史

在分发前先定位当前 workspace 的对话记录。系统提示会给出该 workspace 的 `agent-transcripts/` 目录。只使用该路径。不要跨 `~/.cursor/projects/*/` 做 glob。那会跨越 workspace 边界，读取无关项目的私人对话。

在该范围内巡查近期智能体对话，寻找重复模式。对历史切片并行运行多个子代理（例如最近 2-4 周，切成 3 片以保证每片材料充足）。按 **poteto-mode** skill 的 Subagents 一节，为每个子代理的推理层级按任务选择。每个切片挖掘子代理读取父代理提供的 workspace 作用域路径下的对话记录，寻找下列信号，并返回一份简短的结构化模式列表及证据指针。值得默认搜寻的信号：

- 回复偏好（长度、语气、格式、“讲简单点”之类的纠正）
- 委派习惯（子代理、模型、专用工作流、并行度）
- 验证姿态（“完成”意味着什么，单元测试还是实机复现，评审者）
- 代码与行文纪律（风格、引用的原则、lint/format 工具）
- 流程惯例（worktree、提交、PR、评审/合并工具）
- 元偏好（任务中途修 skill、提议新 skill）

在提升某个信号前跨切片交叉核对。在 2 个及以上切片中出现的模式是高置信度。孤立信号很弱，通常丢弃。

### 2. 直接询问用户

挖掘会漏掉尚未出现的意图。使用 `AskQuestion` 工具（结构化多选），而不是让用户从零打字。

形态：一到两个问题，每个 4-6 个选项，类别问题设 `allow_multiple: true`。先宽泛（“哪些方面最重要？”），再对选中的方面用具体选项追问。结构化轮次之后，用一个自由文本问题捕捉选项遗漏的内容。

不要一次抛 20 个问题。

### 3. 聚类发现

把合并后的信号分组成章节。常见章节（只采用适用的）：

- **回复风格**：长度、语气、格式。
- **自主性**：不问就做多少、MCP 工具使用。
- **先理解**：界定或调查改动时该用哪些 skill。
- **子代理**：默认、并行、模型与任务匹配、专用工作流。
- **行文/代码纪律**：原则、lint 工具、风格指南。
- **评审与验证**：复现姿态、验证 skill、实机测试工具。
- **流程**：git worktree、提交、PR、评审/合并工具。
- **Skills**：skill 撰写习惯、先修 skill、提议新 skill。

**poteto-mode** skill 展示了形态。读它以把握粒度。不要照抄其内容。用户的规则与 poteto-mode 的并不相同。

### 4. 起草 skill

使用 Cursor 内置的 `create-skill` skill 撰写该 skill。放置位置：

- 路径：保留已有 mode skill 的分类。新建 mode 时，若仓库已为该 handle 建立个人分类，用 `.cursor/skills/<handle>/<handle>-mode/SKILL.md`。否则默认用项目中的 `.cursor/skills/<handle>-mode/SKILL.md`（若用户偏好个人 skill，则用 `~/.cursor/skills/<handle>-mode/`）。
- Handle：用户的名字或自选标识符。
- Frontmatter `description`：以其名字 + `/<handle>-mode` + “按他的风格工作”触发，不要用“写代码”或“评审 PR”这类泛化关键词。
- Frontmatter 格式：遵循 `create-skill` 的 YAML 规则。`description` 保持为单个 YAML 标量。当标点或换行需要时，给它加引号，或用 `description: >-` 配缩进续行。
- Frontmatter `disable-model-invocation: true` 为默认。仅当用户明确希望其 mode 在每一轮都生效时才关闭。

### 5. 迭代行文

对每一行应用 **unslop** skill 和 `create-skill` 的写作准则。

把草稿给用户看并收集反馈。预期多轮迭代。果断删减。mode skill 不是手册。

### 6. 落地

在基于 main 的 worktree 中作业。提交并开 PR。不要直接推到 main。

## 护栏

- **不要对单次对话过拟合。** 一次提出又在另一次被否定的偏好是噪音。需要多次出现才能固化。
- **不要耍聪明。** 复述其他 skill 的内容、发明比喻，或为智能体读者写“诗意”行文，都是只有成本没有收益。保持可操作。
- **引用而非内联。** 用户依赖的其他 skill 应以路径引用出现，而不是粘贴摘录。用户在其他地方维护的原则文档同理。
- **章节保持最少。** 只有当用户在该处有具体的、非默认的规则时才加章节。“清晰沟通”不是一个章节。“短段落。比较选项时用表格。仅在条目真正并列时用项目符号。”才是。
- **命名保持通用。** 祈使句中用“用户”或“人”，不要用作者的名字。
- **不要强求对称。** 如果用户没有值得写下的流程规则，就整节跳过流程。

## 评估

`-mode` skill 是主观输出。`create-skill` 式的测试/迭代基准循环在这里没用。与用户凭感觉核对：读起来像他吗？漏了什么吗？然后就交付。

仅当该 skill 的触发准确性在实践中确实成为问题时，才运行描述优化循环。

## 何时不用

- 用户要任务专用的 skill（而非工作惯例）：单用 `create-skill`，无需挖掘。
- 用户想固化某一个狭窄工作流（例如“我怎么写提交信息”）。那是普通 skill，不是 mode skill。

