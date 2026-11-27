# MediaPlayerFixed

TLC 到达了 11 个状态和 57 个步骤。图表绘制了 7 个状态和 13 条箭头。
步骤 a call comes in 会同时改变 Playback 和 Volume。
步骤 you press stop 会同时改变 Playback 和 Volume。
步骤 the track ends 会同时改变 Playback 和 Volume。

## 成立的规则
TypeOK, LoudWhenStopped, NoDeadlock
