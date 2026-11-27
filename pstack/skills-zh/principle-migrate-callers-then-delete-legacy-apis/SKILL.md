---
name: principle-migrate-callers-then-delete-legacy-apis
description: "在引入新的内部 API 而旧调用方仍然存在时适用。在同一波里迁移调用方并删除旧 API，而不是保留兼容层。"
disable-model-invocation: true
---

# 先迁移调用方，再删除遗留 API

- 更新测试以断言新的契约，并删除只保护重构前实现细节的测试

**适用条件：**
- 没有外部用户依赖向后兼容
- 项目能承受协同的破坏性改动
- 新 API 是简化或重构计划的一部分
