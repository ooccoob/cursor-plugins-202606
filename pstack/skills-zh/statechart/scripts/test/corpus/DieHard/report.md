# DieHard

TLC 到达了 16 个状态和 96 个步骤。图表绘制了 16 个状态和 58 条箭头。
图表不绘制 38 个停留在同一个图表状态内的步骤。

## NotSolved 被违反
最短路径有 6 步：
0. big=0 small=0
1. FillBig: big=5 small=0
2. BigToSmall: big=2 small=3
3. EmptySmall: big=2 small=0
4. BigToSmall: big=0 small=2
5. FillBig: big=5 small=2
6. BigToSmall: big=4 small=3

## 成立的规则
TypeOK, NoDeadlock
