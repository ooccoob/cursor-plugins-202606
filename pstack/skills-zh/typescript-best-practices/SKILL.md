---
name: typescript-best-practices
description: TypeScript 最佳实践。在阅读或编辑任何 .ts 或 .tsx 文件时使用。
paths: ["**/*.ts", "**/*.tsx"]
disable-model-invocation: true
---

# TypeScript 最佳实践

先应用 **type-system-discipline** 原则 Skill。

| 规则 | 概要 |
|------|---------|
| 可辨识联合 | 用 `kind` 字面量判别字段建模各变体，使不可能的状态无法被表示。不要用可选字段堆。 |
| 品牌类型 | 用 `& { readonly __brand: "X" }` 为原始类型打上品牌，使它们不会被混用。在边界处校验一次。品牌来自具校验能力的类型守卫（`input is AgentId`），绝不来自 `as`。 |
| 构造式建模 | 把形状设计成非法值无法被构造出来。非空用 `[T, ...T[]]`，偶数长度用 `[T, T][]`，区间用 `start` 加 `duration`。不要靠运行时守卫，也不要指望 refinement types。 |
| 最简单的全函数类型 | 只要对 `T[]` 的每个操作都是全函数，就保留 `T[]`。只在松散类型迫使你写 `!`、类型断言或"永不发生"抛出时，才收紧为 `NonEmpty<T>`。 |
| 用 `unknown` 而非 `any` | 外部数据是 `unknown`。 |
| 模式优先于守卫 | 在手工编写逐属性类型守卫之前，先使用仓库的运行时 schema 库，并从 schema 推断类型，例如 `z.infer`。 |
| 禁止 `as` 类型断言 | 每个 `as` 都是一次等待发生的运行时崩溃。只在校验之后才断言。 |
| 类型收窄层级 | 判别字段 switch > `in` 运算符 > `typeof`/`instanceof` > 用户定义类型守卫 > `as`。 |
| 类型守卫 | 必须验证其断言。说谎的守卫比 `as` 更糟，因为 bug 藏在一个声称安全的名称后面。命名为 `isX` 或 `hasX`。 |
| 穷尽性 | 在 default 分支内联 `const _exhaustive: never = x;`，这样新增变体时编译器会报错。 |
| `satisfies` 优先于 `as` | 校验值而不放宽字面量类型。 |
| 边界校验 | 在数据进入处解析，转成具名领域类型。`Record<string, unknown>`（无论怎么写）止步于该解析。内部信任类型。参见 **boundary-discipline** 原则 Skill。 |
| 从 schema 派生类型 | 在声明新 interface 之前，先用 `Pick`/`Omit`/`Parameters`/`ReturnType`/`Awaited`/`typeof`。 |
| 对象参数 | 传对象而不是位置参数，使参数顺序自解释。热路径上除外（逐帧渲染、分词器、解析器）。 |
| 真实测试 | 能运行的不要 mock。优先使用框架的真实测试原语并配合泄漏/可释放检查，在运行中的构建里验证 UI。只 mock 本地无法运行的部分。 |
| 结构化遥测 | 优先使用结构化日志诊断，带有足够上下文以便从 id 开始排查。交付代码中不要有 `console.log`。 |

示例：`references/patterns.md`。