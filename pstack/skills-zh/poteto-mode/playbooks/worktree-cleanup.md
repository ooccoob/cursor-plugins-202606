### 工作树与模拟器清理（Worktree and simulator cleanup）

1. 先快照再审计。记录 `df -h /`，然后运行 `scripts/worktree-audit.sh [-b <pr-base-ref>] [repo-path]`（principle-build-the-lever）。不带 `-b` 时它对照 `origin/HEAD` 检查 `MERGED`，所以当 PR 指向其他分支时要传 `-b origin/<branch>`。它从 `git worktree list` 读取路径，绝不手敲，因为手敲的 `myrepo-worktrees/x` 会漏掉那个位于 `.cursor/worktrees/myrepo/x` 的工作树（principle-encode-lessons-in-structure）。它按大小、年龄、合并状态、未提交工作、PR 状态以及最近接触过它的会话，为每个工作树分类，然后给出分桶建议。会话记录扫描很慢，所以放到后台跑。
2. 分桶只是建议，不是许可。被钉住的和活跃的会话才是真实产物（principle-prove-it-works）。从用户或侧边栏拿到这个集合，逐个候选交叉核对。这个杠杆曾经把一个用户钉住的工作树标成 `safe`，所以以钉住的集合为准。
3. 删除前先核实使用情况。对每个 `verify-recent-chat` 行，或任何你存疑的项，把子代理分发出去读会话记录，报告该会话是否被钉住或仍在进行，以及它触及哪些工作树（principle-guard-the-context-window，会话记录体量很大）。被钉住的会话会通过后台子代理把竞技场和复现用的树派生到同级工作树里，那些树即使名字从未出现在侧边栏中，也仍在使用中。按 Subagents 章节所述，为每个子代理按任务选择推理档位。
4. 遇到不可逆的损失就暂停。`wip:N` 表示有 N 处已跟踪的未提交编辑。先展示 diff 并拿到决定，因为移除一个干净的工作树还能从其分支恢复，而未提交的工作会永久丢失。`scratch:N` 是未跟踪的一次性文件，可以安全丢弃，但要列出文件名。按自主性约定，干净、已合并且未被使用的继续执行。`wip` 与使用中的要暂停。
5. 清理已确认的集合。逐路径执行 `git worktree remove --force <path>`。如果目录因为被忽略的构建产物而残留，就 `rm -rf` 它，然后 `git worktree prune`。分支引用会保留，所以不会丢提交。用 `df -h /` 确认并重新列出。
6. 模拟器与其他可回收项。模拟器通常是下一个最大的收益点。`xcrun simctl --set testing delete all`（XCTestDevices 克隆）、`xcrun simctl delete unavailable`，以及 `xcrun simctl runtime list` 之后对旧运行时执行 `runtime delete <id>`。需要时还有更多：Xcode 的 `DerivedData` 与 `iOS DeviceSupport`、`~/Library/Application Support/Cursor`（`state.vscdb.backup`，以及 `snapshots/roots/<root>`——当某个以你曾作为工作区打开的文件夹命名的 `<root>` 会膨胀）、包管理器缓存（pnpm、uv、brew、yarn）。只清用户没有说需要保留的缓存。

这是唯一一个会在删除用户状态时没有代码评审兜底的特性手册，所以上面的那些门禁就是评审。

**回复：** 前后的 `df -h /` 及回收出的空间，已清理的工作树，以及每个被保留项的一行理由（正被哪个会话使用，或有未提交的工作）。
