# CounterDeadlock

TLC 到达了 4 个状态和 3 个步骤。图表绘制了 4 个状态和 4 条箭头。
1 个被约束排除的步骤终止了某条规则的路径，图表把它画了进来。TLC 会在这样的步骤之后检查规则，但不会真正执行该步骤。
图表只标记 TLC 报告的死锁。在 CONSTRAINT 或 ACTION_CONSTRAINT 之下，图表中没有任何步骤的状态仍可能存在被约束排除掉的步骤，TLC 不会把它算作死锁。

## NotThree 被违反
最短路径有 1 步：
0. 0
1. Jump: 3

## NoDeadlock 被违反
最短路径有 3 步：
0. 0
1. Inc: 1
2. Inc: 2
3. Inc: 3
