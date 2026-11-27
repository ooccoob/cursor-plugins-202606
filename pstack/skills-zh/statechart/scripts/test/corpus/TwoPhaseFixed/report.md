# TwoPhaseFixed

TLC 到达了 56 个状态和 142 个步骤。图表绘制了 10 个状态和 12 条箭头。
图表不绘制 45 个停留在同一个图表状态内的步骤。
步骤 RMPrepare 每次只改变 r1 和 r2 中的一个。
步骤 RMChooseToAbort 每次只改变 r1 和 r2 中的一个。
步骤 RMRcvAbortMsg 每次只改变 r1 和 r2 中的一个。
步骤 RMRcvCommitMsg 每次只改变 r1 和 r2 中的一个。

## 成立的规则
TPTypeOK, TCConsistent, NoDeadlock
