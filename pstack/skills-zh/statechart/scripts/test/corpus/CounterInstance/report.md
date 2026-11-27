# CounterInstance

TLC 到达了 3 个状态和 3 个步骤。图表绘制了 3 个状态和 3 条箭头。

## ReachesThree 被违反
TLC 的反例位于 tlc-ReachesThree.out，共 3 步：
0. 0
1. C!Up: 1
2. C!Up: 2
3. C!Back: 1
运行会永远在 "1" 和 "2" 之间循环。

## 成立的规则
NoDeadlock
