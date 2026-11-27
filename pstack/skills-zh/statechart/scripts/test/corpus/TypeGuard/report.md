# TypeGuard

TLC 到达了 3 个状态和 2 个步骤。图表绘制了 3 个状态和 2 条箭头。
TLC 以退出码 76 中止了绘制运行，因此图表只绘制它在停止前已经到达的状态。

## TypeOK 被违反
最短路径有 2 步：
0. 0
1. Next: 1
2. Next: 2

## 未检查的规则
NeedsTypeOK, NoDeadlock
TLC 在以退出码 76 停止之前未检查这些规则：
```
Error: Evaluating invariant NeedsTypeOK failed.
Attempted to apply tuple
<<"zero", "one">>
to integer 3 which is out of domain.
Error: The behavior up to this point is:
State 1: <Initial predicate>
x = 0

State 2: <Next line 6, col 9 to line 6, col 27 of module TypeGuard>
x = 1

State 3: <Next line 6, col 9 to line 6, col 27 of module TypeGuard>
x = 2
```
