# HiddenClock

TLC 到达了 2 个状态和 2 个步骤。图表绘制了 2 个状态和 1 条箭头。
图表不绘制 1 个停留在同一个图表状态内的步骤。
使用 VIEW 时，TLC 对每组被视为相同的状态只保留一个代表。箭头可能指向该代表，而不是步骤实际到达的状态。

## EndsAtZero 被违反
TLC 的反例位于 tlc-EndsAtZero.out，共 1 步：
0. x=0 clock=0
1. Tick: x=1 clock=1
运行会永远停在 "x=1 clock=1"。
