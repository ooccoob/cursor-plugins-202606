---
name: principle-laziness-protocol
description: "在重构、评估 diff 规模，或想增加抽象、层与信号透传时适用。倾向删除，倾向能解决问题的最小改动。"
disable-model-invocation: true
---

# 惰性原则

- **合并决策。** 不要在多个地方重复同一个选择。把它放到唯一真相来源之后，并把结果作为简单的 flag 传递。
- **最小化 diff。** 做能解决问题的最小改动。更少的行胜过“优雅”的样板。
