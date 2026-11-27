---
name: no-comments
description: "生成 Comment Sicko，修复被接受的发现，并为声称的约束提供固化方案。"
disable-model-invocation: true
---

# 不加注释（No comments）

生成 Comment Sicko。对被接受的发现采取行动。

服从 Comment Sicko 的新鲜视角。

## 范围

使用调用方给出的文件或 diff。否则使用当前 diff 对比基线分支，默认 `main`，包含工作树。

## 步骤

1. 用 `subagent_type: "comment-sicko"` 生成 `Task`。传入范围。按 **poteto-mode** 技能的 Subagents 章节，为每个子代理挑选适合该任务的推理等级。不要复述它的规则。
2. 检查它的报告与 diff。拒绝应用代码的改动、范围越界、受异常保护的删除、陈述错误的 `MUST KILL` 理由，以及把保留的刻意代码当作有罪的标记。针对我方代码的意外情况重塑标记仍可执行。不要恢复那些注释。保留项只有在证明它涉及我们无法改变的东西时才存活。审计被漏掉的范围内 lint 与 TypeScript 抑制。正确性或安全性相关的抑制仍然是可执行的 `MUST KILL`。只有给出确切的异常和范围内证明才恢复删除。在接受单薄的 `IMPORTANT` 或 `do not remove` 的删除或保留之前，追踪其符号或对它运行 `/why`。如果删除含糊，不要恢复。如果保留被驳倒或仍然含糊，删掉它。回退并以点名失败的方式重跑一份被拒绝的报告。第二次仍被拒绝，就把它记为未决，并让 `/no-comments` 失败。
3. 直接修复简单的被接受标记：删掉死路径、去掉参数，或使用真实 API。如果任何修复需要形态，对已接受集合及周边代码运行一次 `/architect`。停在草图。Architect 定形态。步骤 4 负责实现。
4. 在范围内实现最小的根因修复。移除每一个被点名的绕过手段。如果根因在范围之外，落地最小的范围内修复并把其余记为未决。**principle-fix-root-causes** 与 **principle-redesign-from-first-principles** 技能只指导意图。两者都不授权扩大围栏，也不授权修复围栏之外的实例。绝不要附加症状性防护。
5. 约束注释会说 `do not remove`、`do not change wording` 或 `talk to X before changing`。留下关于我们无法改变之事的保留项。提供最便宜的范围内类型、运行时、测试或 CI lint 方案。等待交互式批准。无人值守和 eval 需要调用方预先批准。如获批准，先固化再删除。否则删除、把该约束记为未决，并勾画范围外的工作。
6. 报告删除数量、被恢复的注释、重跑情况、architect 草图、修复、固化提议、已固化项、未被强制的约束，以及其他未决工作。
