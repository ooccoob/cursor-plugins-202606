# MediaPlayerProps

TLC 到达了 12 个状态和 64 个步骤。图表绘制了 7 个状态和 13 条箭头。
步骤 a call comes in 会同时改变 Playback 和 Volume。
步骤 the track ends 会同时改变 Playback 和 Volume。
步骤 you press stop 会同时改变 Playback 和 Volume。

## EventuallyPlays 被违反
TLC 的反例位于 tlc-EventuallyPlays.out，共 0 步：
0. Playback Stopped, Volume Normal volume
运行会永远停在 "Playback Stopped, Volume Normal volume"。

## QuietWhenStopped 被违反
TLC 的反例位于 tlc-QuietWhenStopped.out，共 1 步：
0. Playback Stopped, Volume Normal volume
1. you turn it up: Playback Stopped, Volume Loud

## 成立的规则
TypeOK, NoDeadlock, EventuallyStops, StaysTyped
