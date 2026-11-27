# LoginParallel

TLC 到达了 12 个状态和 29 个步骤。图表绘制了 7 个状态和 10 条箭头。
步骤 ThePasswordIsWrong 会同时改变 Session 和 Tries。
步骤 ThePasswordIsRight 会同时改变 Session 和 Tries。

## SignedInWhileLocked 被违反
最短路径有 5 步：
0. Session Signed out, Tries No wrong tries
1. ThePasswordIsWrong: Session Signed out, Tries 1 wrong try
2. ThePasswordIsWrong: Session Signed out, Tries 2 wrong tries
3. ThePasswordIsWrong: Session Signed out, Tries Locked out
4. YouSubmitAPassword: Session Checking the password, Tries Locked out
5. ThePasswordIsRight: Session Signed in, Tries Locked out

## 成立的规则
TypeOK, NoDeadlock
