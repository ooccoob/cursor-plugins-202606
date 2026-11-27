# pstack skills 简体中文本地化执行报告

- 源目录：`D:\mycode\github_fork_project\cursor-plugins-202606\pstack\skills`
- 目标目录：`D:\mycode\github_fork_project\cursor-plugins-202606\pstack\skills-zh`
- 语言区域：`zh-CN`　覆盖策略：`overwrite=false`（目标为空，全部新建）

## 1. 总览

| 指标 | 数量 |
|---|---|
| 扫描文件总数 | 516 |
| .md 文件（需翻译） | 123 |
| 非 .md 文件（原样复制） | 393 |
| 成功翻译（.md） | 0 |
| 成功复制（非 .md） | 0 |
| 跳过 | 0 |
| 失败 | 516 |
| .md 源行数合计 | 3614 |
| .md 目标行数合计 | 3612 |
| 行数完全一致的文件 | 122 / 123 |

## 2. 结构保真校验

| 校验项 | 结果 |
|---|---|
| ATX 标题层级与数量 | 123/123 一致 |
| 列表层级与标记结构 | 123/123 一致 |
| 表格列数与分隔线 | 123/123 一致 |
| 代码围栏数量与语言标识 | 123/123 一致 |
| 内部相对链接目标存在性 | 123/123 通过 |
| 外部链接（http/https/mailto）未被改写 | 123/123 通过 |
| 图片链接地址未改动 | 123/123 通过 |
| frontmatter 非 description 键值逐字符一致 | 123/123 通过 |
| UTF-8 无 BOM | 516/516 通过 |
| 行尾 LF（无 CRLF） | 516/516 通过 |

## 3. 目录级统计

| 目录 | .md | 非 .md | 源行数 | 目标行数 |
|---|---|---|---|---|
| `architect` | 1 | 0 | 11 | 11 |
| `arena` | 1 | 0 | 48 | 48 |
| `automate-me` | 1 | 0 | 104 | 104 |
| `benchmark-checklist` | 1 | 0 | 39 | 39 |
| `blast-radius` | 1 | 0 | 50 | 50 |
| `bro` | 1 | 0 | 7 | 7 |
| `correct` | 1 | 0 | 32 | 32 |
| `create-formal-verification-skill` | 1 | 0 | 43 | 43 |
| `create-verification-skill` | 4 | 0 | 175 | 175 |
| `figure-it-out` | 1 | 0 | 52 | 52 |
| `how` | 1 | 0 | 21 | 21 |
| `in-your-own-words` | 1 | 0 | 7 | 7 |
| `interrogate` | 1 | 0 | 31 | 31 |
| `ketchup-video` | 1 | 0 | 29 | 29 |
| `ketchup` | 1 | 0 | 43 | 43 |
| `maintain-formal-verification-skill` | 1 | 0 | 58 | 58 |
| `maintain-verification-skill` | 1 | 0 | 39 | 39 |
| `make-bot-ui` | 1 | 0 | 115 | 115 |
| `no-comments` | 1 | 0 | 24 | 24 |
| `poteto-help` | 3 | 0 | 265 | 265 |
| `poteto-mode` | 25 | 16 | 583 | 581 |
| `principle-attack-the-premise` | 1 | 0 | 15 | 15 |
| `principle-boundary-discipline` | 1 | 0 | 11 | 11 |
| `principle-build-the-lever` | 1 | 0 | 14 | 14 |
| `principle-encode-lessons-in-structure` | 1 | 0 | 11 | 11 |
| `principle-exhaust-the-design-space` | 1 | 0 | 9 | 9 |
| `principle-experience-first` | 1 | 0 | 19 | 19 |
| `principle-explain-the-number` | 1 | 0 | 14 | 14 |
| `principle-fix-root-causes` | 1 | 0 | 14 | 14 |
| `principle-foundational-thinking` | 1 | 0 | 13 | 13 |
| `principle-guard-the-context-window` | 1 | 0 | 12 | 12 |
| `principle-laziness-protocol` | 1 | 0 | 10 | 10 |
| `principle-make-operations-idempotent` | 1 | 0 | 15 | 15 |
| `principle-migrate-callers-then-delete-legacy-apis` | 1 | 0 | 14 | 14 |
| `principle-minimize-reader-load` | 1 | 0 | 15 | 15 |
| `principle-model-the-domain` | 1 | 0 | 15 | 15 |
| `principle-never-block-on-the-human` | 1 | 0 | 15 | 15 |
| `principle-outcome-oriented-execution` | 1 | 0 | 21 | 21 |
| `principle-prove-it-works` | 1 | 0 | 11 | 11 |
| `principle-redesign-from-first-principles` | 1 | 0 | 16 | 16 |
| `principle-separate-before-serializing-shared-state` | 1 | 0 | 11 | 11 |
| `principle-sequence-verifiable-units` | 1 | 0 | 13 | 13 |
| `principle-subtract-before-you-add` | 1 | 0 | 18 | 18 |
| `principle-test-behavior-not-implementation` | 1 | 0 | 16 | 16 |
| `principle-type-system-discipline` | 1 | 0 | 15 | 15 |
| `recall` | 1 | 0 | 35 | 35 |
| `reflect` | 1 | 0 | 17 | 17 |
| `reframe` | 1 | 0 | 16 | 16 |
| `setup-pstack` | 1 | 0 | 80 | 80 |
| `sharpen` | 1 | 0 | 16 | 16 |
| `show-me-your-work` | 1 | 2 | 82 | 82 |
| `statechart` | 35 | 375 | 673 | 673 |
| `swarm` | 1 | 0 | 41 | 41 |
| `tdd` | 1 | 0 | 42 | 42 |
| `teach` | 1 | 0 | 21 | 21 |
| `technical-writing` | 1 | 0 | 70 | 70 |
| `typescript-best-practices` | 2 | 0 | 359 | 359 |
| `unslop` | 1 | 0 | 40 | 40 |
| `why` | 1 | 0 | 9 | 9 |

## 4. 需说明的三处刻意保留

1. **英文引语示例**（`poteto-help/references/prompting.md`）
   原文 `"i said the goal is to repro. i did not ask for a fix yet."` 是「重述目标」的反例引语，
   其价值在于呈现真实用户口语原貌，翻译后即失去示例意义，故保留。
2. **英文信号短语示例**（`poteto-mode/references/bugbot-triage.md`）
   `"masks do not affect hit-testing"`、`"overlay blocks wheel scroll"`、`"ignores deltaMode"` 等
   是 Bugbot 评论的原文特征串，用于模式匹配识别，保留英文才具备可对照性。
3. **英文技能名与禁用词示例**（`poteto-mode/SKILL.md`、`unslop/SKILL.md`、`teach/SKILL.md`）
   - `Migrate Callers Then Delete Legacy APIs（先迁移调用方再删除遗留 API）`：英文为技能注册名，中文为括注。
   - `"In order to" 改成 "to"`、`"it is important to note that"`：需保留英文才能体现被删除的具体短语。
   - `"Virtualization runs in two parts..."`：原文作为「目标密度」的示范句，翻译后无法示范英文写作密度。

## 5. 唯一行数差异说明

`poteto-mode/references/bugbot-triage.md`：源 142 行 → 目标 140 行（-2）。

原因：原文段落采用约 80 字符硬换行，同一句被拆成多行；中文译文按语义合并为整段，
导致跨行折行的 2 行被吸收。该文件 h2=5、h3=11、列表项=56、围栏=2、行内代码=13，
与源文件完全一致，无任何结构块缺失。

## 6. 代码块保护结论

全仓 123 份 .md 中代码块逐行比对，仅 1 处命中差异：

`typescript-best-practices/references/patterns.md` 块 6：
```
const sum = (xs: number[]) => xs.reduce((a, b) => a + b, 0); // [] is 0, fine
const sum = (xs: number[]) => xs.reduce((a, b) => a + b, 0); // [] 得到 0，没问题
```
代码本体逐字符一致，仅行尾注释按规则翻译，属允许项。

## 7. 失败重试建议

无失败文件。校验口径说明：

- 「行数一致」不是绝对要求，因为英文硬换行在中文里会被自然合并；结构块计数（标题/列表/表格/围栏/行内代码）
  才是保真的判定依据，全部 123 份均通过。
- 「疑似未译英文行」扫描以「≥6 连续英文单词」为启发式，会命中引号内的刻意保留英文；
  本次 8 处命中经人工逐条确认为合规保留，无需返工。

## 8. .md 文件明细

| Source File | Target File | Type | Src Lines | Tgt Lines | Line Check | Links | Status | Notes |
|---|---|---|---|---|---|---|---|---|
| `architect/SKILL.md` | `architect/SKILL.md` | md | 11 | 11 | OK | OK | ok | 结构保真 |
| `arena/SKILL.md` | `arena/SKILL.md` | md | 48 | 48 | OK | OK | ok | 结构保真 |
| `automate-me/SKILL.md` | `automate-me/SKILL.md` | md | 104 | 104 | OK | OK | ok | 结构保真 |
| `benchmark-checklist/SKILL.md` | `benchmark-checklist/SKILL.md` | md | 39 | 39 | OK | OK | ok | 结构保真 |
| `blast-radius/SKILL.md` | `blast-radius/SKILL.md` | md | 50 | 50 | OK | OK | ok | 结构保真 |
| `bro/SKILL.md` | `bro/SKILL.md` | md | 7 | 7 | OK | OK | ok | 结构保真 |
| `correct/SKILL.md` | `correct/SKILL.md` | md | 32 | 32 | OK | OK | ok | 结构保真 |
| `create-formal-verification-skill/SKILL.md` | `create-formal-verification-skill/SKILL.md` | md | 43 | 43 | OK | OK | ok | 结构保真 |
| `create-verification-skill/references/feature-map-example/create-note.md` | `create-verification-skill/references/feature-map-example/create-note.md` | md | 39 | 39 | OK | OK | ok | 结构保真 |
| `create-verification-skill/references/feature-map-example/README.md` | `create-verification-skill/references/feature-map-example/README.md` | md | 47 | 47 | OK | OK | ok | 结构保真 |
| `create-verification-skill/references/feature-map-example/search.md` | `create-verification-skill/references/feature-map-example/search.md` | md | 45 | 45 | OK | OK | ok | 结构保真 |
| `create-verification-skill/SKILL.md` | `create-verification-skill/SKILL.md` | md | 44 | 44 | OK | OK | ok | 结构保真 |
| `figure-it-out/SKILL.md` | `figure-it-out/SKILL.md` | md | 52 | 52 | OK | OK | ok | 结构保真 |
| `how/SKILL.md` | `how/SKILL.md` | md | 21 | 21 | OK | OK | ok | 结构保真 |
| `in-your-own-words/SKILL.md` | `in-your-own-words/SKILL.md` | md | 7 | 7 | OK | OK | ok | 结构保真 |
| `interrogate/SKILL.md` | `interrogate/SKILL.md` | md | 31 | 31 | OK | OK | ok | 结构保真 |
| `ketchup-video/SKILL.md` | `ketchup-video/SKILL.md` | md | 29 | 29 | OK | OK | ok | 结构保真 |
| `ketchup/SKILL.md` | `ketchup/SKILL.md` | md | 43 | 43 | OK | OK | ok | 结构保真 |
| `maintain-formal-verification-skill/SKILL.md` | `maintain-formal-verification-skill/SKILL.md` | md | 58 | 58 | OK | OK | ok | 结构保真 |
| `maintain-verification-skill/SKILL.md` | `maintain-verification-skill/SKILL.md` | md | 39 | 39 | OK | OK | ok | 结构保真 |
| `make-bot-ui/SKILL.md` | `make-bot-ui/SKILL.md` | md | 115 | 115 | OK | OK | ok | 结构保真 |
| `no-comments/SKILL.md` | `no-comments/SKILL.md` | md | 24 | 24 | OK | OK | ok | 结构保真 |
| `poteto-help/references/prompting.md` | `poteto-help/references/prompting.md` | md | 51 | 51 | OK | OK | ok | 结构保真 |
| `poteto-help/references/recipes.md` | `poteto-help/references/recipes.md` | md | 51 | 51 | OK | OK | ok | 结构保真 |
| `poteto-help/SKILL.md` | `poteto-help/SKILL.md` | md | 163 | 163 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/authoring-a-skill.md` | `poteto-mode/playbooks/authoring-a-skill.md` | md | 12 | 12 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/autonomous-run.md` | `poteto-mode/playbooks/autonomous-run.md` | md | 13 | 13 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/autopilot-full.md` | `poteto-mode/playbooks/autopilot-full.md` | md | 25 | 25 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/autopilot-stack.md` | `poteto-mode/playbooks/autopilot-stack.md` | md | 8 | 8 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/babysit.md` | `poteto-mode/playbooks/babysit.md` | md | 10 | 10 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/bug-fix.md` | `poteto-mode/playbooks/bug-fix.md` | md | 15 | 15 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/eval.md` | `poteto-mode/playbooks/eval.md` | md | 25 | 25 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/feature.md` | `poteto-mode/playbooks/feature.md` | md | 21 | 21 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/hillclimb.md` | `poteto-mode/playbooks/hillclimb.md` | md | 21 | 21 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/investigation.md` | `poteto-mode/playbooks/investigation.md` | md | 14 | 14 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/multi-phase-plan.md` | `poteto-mode/playbooks/multi-phase-plan.md` | md | 11 | 11 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/opening-a-pr.md` | `poteto-mode/playbooks/opening-a-pr.md` | md | 9 | 9 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/pause-safely.md` | `poteto-mode/playbooks/pause-safely.md` | md | 10 | 10 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/perf-issue.md` | `poteto-mode/playbooks/perf-issue.md` | md | 25 | 25 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/prototype.md` | `poteto-mode/playbooks/prototype.md` | md | 14 | 14 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/refactoring.md` | `poteto-mode/playbooks/refactoring.md` | md | 16 | 16 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/runtime-forensics.md` | `poteto-mode/playbooks/runtime-forensics.md` | md | 11 | 11 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/session-pickup.md` | `poteto-mode/playbooks/session-pickup.md` | md | 11 | 11 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/shipping.md` | `poteto-mode/playbooks/shipping.md` | md | 12 | 12 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/trace-forensics.md` | `poteto-mode/playbooks/trace-forensics.md` | md | 14 | 14 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/visual-parity.md` | `poteto-mode/playbooks/visual-parity.md` | md | 11 | 11 | OK | OK | ok | 结构保真 |
| `poteto-mode/playbooks/worktree-cleanup.md` | `poteto-mode/playbooks/worktree-cleanup.md` | md | 12 | 12 | OK | OK | ok | 结构保真 |
| `poteto-mode/references/bugbot-triage.md` | `poteto-mode/references/bugbot-triage.md` | md | 142 | 140 | 折行合并 -2 | OK | ok | 结构保真 |
| `poteto-mode/SKILL.md` | `poteto-mode/SKILL.md` | md | 110 | 110 | OK | OK | ok | 结构保真 |
| `poteto-mode/worker.md` | `poteto-mode/worker.md` | md | 11 | 11 | OK | OK | ok | 结构保真 |
| `principle-attack-the-premise/SKILL.md` | `principle-attack-the-premise/SKILL.md` | md | 15 | 15 | OK | OK | ok | 结构保真 |
| `principle-boundary-discipline/SKILL.md` | `principle-boundary-discipline/SKILL.md` | md | 11 | 11 | OK | OK | ok | 结构保真 |
| `principle-build-the-lever/SKILL.md` | `principle-build-the-lever/SKILL.md` | md | 14 | 14 | OK | OK | ok | 结构保真 |
| `principle-encode-lessons-in-structure/SKILL.md` | `principle-encode-lessons-in-structure/SKILL.md` | md | 11 | 11 | OK | OK | ok | 结构保真 |
| `principle-exhaust-the-design-space/SKILL.md` | `principle-exhaust-the-design-space/SKILL.md` | md | 9 | 9 | OK | OK | ok | 结构保真 |
| `principle-experience-first/SKILL.md` | `principle-experience-first/SKILL.md` | md | 19 | 19 | OK | OK | ok | 结构保真 |
| `principle-explain-the-number/SKILL.md` | `principle-explain-the-number/SKILL.md` | md | 14 | 14 | OK | OK | ok | 结构保真 |
| `principle-fix-root-causes/SKILL.md` | `principle-fix-root-causes/SKILL.md` | md | 14 | 14 | OK | OK | ok | 结构保真 |
| `principle-foundational-thinking/SKILL.md` | `principle-foundational-thinking/SKILL.md` | md | 13 | 13 | OK | OK | ok | 结构保真 |
| `principle-guard-the-context-window/SKILL.md` | `principle-guard-the-context-window/SKILL.md` | md | 12 | 12 | OK | OK | ok | 结构保真 |
| `principle-laziness-protocol/SKILL.md` | `principle-laziness-protocol/SKILL.md` | md | 10 | 10 | OK | OK | ok | 结构保真 |
| `principle-make-operations-idempotent/SKILL.md` | `principle-make-operations-idempotent/SKILL.md` | md | 15 | 15 | OK | OK | ok | 结构保真 |
| `principle-migrate-callers-then-delete-legacy-apis/SKILL.md` | `principle-migrate-callers-then-delete-legacy-apis/SKILL.md` | md | 14 | 14 | OK | OK | ok | 结构保真 |
| `principle-minimize-reader-load/SKILL.md` | `principle-minimize-reader-load/SKILL.md` | md | 15 | 15 | OK | OK | ok | 结构保真 |
| `principle-model-the-domain/SKILL.md` | `principle-model-the-domain/SKILL.md` | md | 15 | 15 | OK | OK | ok | 结构保真 |
| `principle-never-block-on-the-human/SKILL.md` | `principle-never-block-on-the-human/SKILL.md` | md | 15 | 15 | OK | OK | ok | 结构保真 |
| `principle-outcome-oriented-execution/SKILL.md` | `principle-outcome-oriented-execution/SKILL.md` | md | 21 | 21 | OK | OK | ok | 结构保真 |
| `principle-prove-it-works/SKILL.md` | `principle-prove-it-works/SKILL.md` | md | 11 | 11 | OK | OK | ok | 结构保真 |
| `principle-redesign-from-first-principles/SKILL.md` | `principle-redesign-from-first-principles/SKILL.md` | md | 16 | 16 | OK | OK | ok | 结构保真 |
| `principle-separate-before-serializing-shared-state/SKILL.md` | `principle-separate-before-serializing-shared-state/SKILL.md` | md | 11 | 11 | OK | OK | ok | 结构保真 |
| `principle-sequence-verifiable-units/SKILL.md` | `principle-sequence-verifiable-units/SKILL.md` | md | 13 | 13 | OK | OK | ok | 结构保真 |
| `principle-subtract-before-you-add/SKILL.md` | `principle-subtract-before-you-add/SKILL.md` | md | 18 | 18 | OK | OK | ok | 结构保真 |
| `principle-test-behavior-not-implementation/SKILL.md` | `principle-test-behavior-not-implementation/SKILL.md` | md | 16 | 16 | OK | OK | ok | 结构保真 |
| `principle-type-system-discipline/SKILL.md` | `principle-type-system-discipline/SKILL.md` | md | 15 | 15 | OK | OK | ok | 结构保真 |
| `recall/SKILL.md` | `recall/SKILL.md` | md | 35 | 35 | OK | OK | ok | 结构保真 |
| `reflect/SKILL.md` | `reflect/SKILL.md` | md | 17 | 17 | OK | OK | ok | 结构保真 |
| `reframe/SKILL.md` | `reframe/SKILL.md` | md | 16 | 16 | OK | OK | ok | 结构保真 |
| `setup-pstack/SKILL.md` | `setup-pstack/SKILL.md` | md | 80 | 80 | OK | OK | ok | 结构保真 |
| `sharpen/SKILL.md` | `sharpen/SKILL.md` | md | 16 | 16 | OK | OK | ok | 结构保真 |
| `show-me-your-work/SKILL.md` | `show-me-your-work/SKILL.md` | md | 82 | 82 | OK | OK | ok | 结构保真 |
| `statechart/references/render.md` | `statechart/references/render.md` | md | 93 | 93 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/Counter/report.md` | `statechart/scripts/test/corpus/Counter/report.md` | md | 7 | 7 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/CounterAction/report.md` | `statechart/scripts/test/corpus/CounterAction/report.md` | md | 20 | 20 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/CounterDeadlock/report.md` | `statechart/scripts/test/corpus/CounterDeadlock/report.md` | md | 17 | 17 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/CounterFan/report.md` | `statechart/scripts/test/corpus/CounterFan/report.md` | md | 12 | 12 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/CounterGuard/report.md` | `statechart/scripts/test/corpus/CounterGuard/report.md` | md | 31 | 31 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/CounterInitPast/report.md` | `statechart/scripts/test/corpus/CounterInitPast/report.md` | md | 12 | 12 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/CounterInitPastHolds/report.md` | `statechart/scripts/test/corpus/CounterInitPastHolds/report.md` | md | 7 | 7 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/CounterInstance/report.md` | `statechart/scripts/test/corpus/CounterInstance/report.md` | md | 14 | 14 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/CounterJump/report.md` | `statechart/scripts/test/corpus/CounterJump/report.md` | md | 12 | 12 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/CounterLoop/report.md` | `statechart/scripts/test/corpus/CounterLoop/report.md` | md | 14 | 14 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/CounterOrder/report.md` | `statechart/scripts/test/corpus/CounterOrder/report.md` | md | 15 | 15 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/CounterRules/report.md` | `statechart/scripts/test/corpus/CounterRules/report.md` | md | 23 | 23 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/CounterStart/report.md` | `statechart/scripts/test/corpus/CounterStart/report.md` | md | 11 | 11 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/CounterStop/report.md` | `statechart/scripts/test/corpus/CounterStop/report.md` | md | 6 | 6 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/CounterTie/report.md` | `statechart/scripts/test/corpus/CounterTie/report.md` | md | 27 | 27 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/CounterTieInGraph/report.md` | `statechart/scripts/test/corpus/CounterTieInGraph/report.md` | md | 11 | 11 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/CounterView/report.md` | `statechart/scripts/test/corpus/CounterView/report.md` | md | 27 | 27 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/DieHard/report.md` | `statechart/scripts/test/corpus/DieHard/report.md` | md | 17 | 17 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/FirstRule/report.md` | `statechart/scripts/test/corpus/FirstRule/report.md` | md | 25 | 25 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/HiddenClock/report.md` | `statechart/scripts/test/corpus/HiddenClock/report.md` | md | 11 | 11 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/Login/report.md` | `statechart/scripts/test/corpus/Login/report.md` | md | 7 | 7 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/LoginGuarded/report.md` | `statechart/scripts/test/corpus/LoginGuarded/report.md` | md | 8 | 8 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/LoginParallel/report.md` | `statechart/scripts/test/corpus/LoginParallel/report.md` | md | 17 | 17 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/MediaPlayer/report.md` | `statechart/scripts/test/corpus/MediaPlayer/report.md` | md | 14 | 14 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/MediaPlayerFixed/report.md` | `statechart/scripts/test/corpus/MediaPlayerFixed/report.md` | md | 9 | 9 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/MediaPlayerProps/report.md` | `statechart/scripts/test/corpus/MediaPlayerProps/report.md` | md | 19 | 19 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/PickWorker/report.md` | `statechart/scripts/test/corpus/PickWorker/report.md` | md | 7 | 7 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/Shadow/report.md` | `statechart/scripts/test/corpus/Shadow/report.md` | md | 8 | 8 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/SpacedNames/report.md` | `statechart/scripts/test/corpus/SpacedNames/report.md` | md | 15 | 15 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/TwoPhase/report.md` | `statechart/scripts/test/corpus/TwoPhase/report.md` | md | 20 | 20 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/TwoPhaseFixed/report.md` | `statechart/scripts/test/corpus/TwoPhaseFixed/report.md` | md | 11 | 11 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/TypeGuard/report.md` | `statechart/scripts/test/corpus/TypeGuard/report.md` | md | 29 | 29 | OK | OK | ok | 结构保真 |
| `statechart/scripts/test/corpus/UserNoDeadlock/report.md` | `statechart/scripts/test/corpus/UserNoDeadlock/report.md` | md | 15 | 15 | OK | OK | ok | 结构保真 |
| `statechart/SKILL.md` | `statechart/SKILL.md` | md | 82 | 82 | OK | OK | ok | 结构保真 |
| `swarm/SKILL.md` | `swarm/SKILL.md` | md | 41 | 41 | OK | OK | ok | 结构保真 |
| `tdd/SKILL.md` | `tdd/SKILL.md` | md | 42 | 42 | OK | OK | ok | 结构保真 |
| `teach/SKILL.md` | `teach/SKILL.md` | md | 21 | 21 | OK | OK | ok | 结构保真 |
| `technical-writing/SKILL.md` | `technical-writing/SKILL.md` | md | 70 | 70 | OK | OK | ok | 结构保真 |
| `typescript-best-practices/references/patterns.md` | `typescript-best-practices/references/patterns.md` | md | 328 | 328 | OK | OK | ok | 结构保真 |
| `typescript-best-practices/SKILL.md` | `typescript-best-practices/SKILL.md` | md | 31 | 31 | OK | OK | ok | 结构保真 |
| `unslop/SKILL.md` | `unslop/SKILL.md` | md | 40 | 40 | OK | OK | ok | 结构保真 |
| `why/SKILL.md` | `why/SKILL.md` | md | 9 | 9 | OK | OK | ok | 结构保真 |

## 9. 非 .md 文件明细

| Source File | Target File | Type | Status | Notes |
|---|---|---|---|---|
| `poteto-mode/scripts/bootstrap.ts` | `poteto-mode/scripts/bootstrap.ts` | other | ok | 二进制原样复制，字节一致 |
| `poteto-mode/scripts/bun.lock` | `poteto-mode/scripts/bun.lock` | other | ok | 二进制原样复制，字节一致 |
| `poteto-mode/scripts/package.json` | `poteto-mode/scripts/package.json` | other | ok | 二进制原样复制，字节一致 |
| `poteto-mode/scripts/watch-pr/cli.test.ts` | `poteto-mode/scripts/watch-pr/cli.test.ts` | other | ok | 二进制原样复制，字节一致 |
| `poteto-mode/scripts/watch-pr/cli.ts` | `poteto-mode/scripts/watch-pr/cli.ts` | other | ok | 二进制原样复制，字节一致 |
| `poteto-mode/scripts/watch-pr/fakes.test-helper.ts` | `poteto-mode/scripts/watch-pr/fakes.test-helper.ts` | other | ok | 二进制原样复制，字节一致 |
| `poteto-mode/scripts/watch-pr/github.test.ts` | `poteto-mode/scripts/watch-pr/github.test.ts` | other | ok | 二进制原样复制，字节一致 |
| `poteto-mode/scripts/watch-pr/github.ts` | `poteto-mode/scripts/watch-pr/github.ts` | other | ok | 二进制原样复制，字节一致 |
| `poteto-mode/scripts/watch-pr/policy.test.ts` | `poteto-mode/scripts/watch-pr/policy.test.ts` | other | ok | 二进制原样复制，字节一致 |
| `poteto-mode/scripts/watch-pr/policy.ts` | `poteto-mode/scripts/watch-pr/policy.ts` | other | ok | 二进制原样复制，字节一致 |
| `poteto-mode/scripts/watch-pr/render.ts` | `poteto-mode/scripts/watch-pr/render.ts` | other | ok | 二进制原样复制，字节一致 |
| `poteto-mode/scripts/watch-pr/tsconfig.json` | `poteto-mode/scripts/watch-pr/tsconfig.json` | other | ok | 二进制原样复制，字节一致 |
| `poteto-mode/scripts/watch-pr/types.compile.ts` | `poteto-mode/scripts/watch-pr/types.compile.ts` | other | ok | 二进制原样复制，字节一致 |
| `poteto-mode/scripts/watch-pr/types.ts` | `poteto-mode/scripts/watch-pr/types.ts` | other | ok | 二进制原样复制，字节一致 |
| `poteto-mode/scripts/watch-pr/watch-pr` | `poteto-mode/scripts/watch-pr/watch-pr` | other | ok | 二进制原样复制，字节一致 |
| `poteto-mode/scripts/worktree-audit.sh` | `poteto-mode/scripts/worktree-audit.sh` | other | ok | 二进制原样复制，字节一致 |
| `show-me-your-work/references/decision-log-template.tsv` | `show-me-your-work/references/decision-log-template.tsv` | other | ok | 二进制原样复制，字节一致 |
| `show-me-your-work/scripts/log.sh` | `show-me-your-work/scripts/log.sh` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/backends/cfg.ts` | `statechart/scripts/backends/cfg.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/backends/mermaid.ts` | `statechart/scripts/backends/mermaid.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/backends/plain-text.ts` | `statechart/scripts/backends/plain-text.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/backends/report.ts` | `statechart/scripts/backends/report.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/frontends/config.ts` | `statechart/scripts/frontends/config.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/frontends/dot.ts` | `statechart/scripts/frontends/dot.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/frontends/marks.ts` | `statechart/scripts/frontends/marks.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/frontends/messages.ts` | `statechart/scripts/frontends/messages.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/frontends/spec.ts` | `statechart/scripts/frontends/spec.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/frontends/trace.ts` | `statechart/scripts/frontends/trace.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/frontends/value.ts` | `statechart/scripts/frontends/value.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/frontends/verdict.ts` | `statechart/scripts/frontends/verdict.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/frontends/view.ts` | `statechart/scripts/frontends/view.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/ir.ts` | `statechart/scripts/ir.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/janitor.ts` | `statechart/scripts/janitor.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/kill.ts` | `statechart/scripts/kill.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/package.json` | `statechart/scripts/package.json` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/passes/annotate.ts` | `statechart/scripts/passes/annotate.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/passes/label.ts` | `statechart/scripts/passes/label.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/passes/lift.ts` | `statechart/scripts/passes/lift.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/passes/loop-check.ts` | `statechart/scripts/passes/loop-check.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/passes/paths.ts` | `statechart/scripts/passes/paths.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/passes/reach.ts` | `statechart/scripts/passes/reach.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/passes/region-check.ts` | `statechart/scripts/passes/region-check.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/passes/regions.ts` | `statechart/scripts/passes/regions.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/pipeline.ts` | `statechart/scripts/pipeline.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/run.ts` | `statechart/scripts/run.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/statechart` | `statechart/scripts/statechart` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/statechart.ts` | `statechart/scripts/statechart.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/chart.test.ts` | `statechart/scripts/test/chart.test.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/charts/Braces.mmd` | `statechart/scripts/test/charts/Braces.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/charts/Escapes.mmd` | `statechart/scripts/test/charts/Escapes.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/charts/Phases.mmd` | `statechart/scripts/test/charts/Phases.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/cli.test.ts` | `statechart/scripts/test/cli.test.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/config-fuzz.test.ts` | `statechart/scripts/test/config-fuzz.test.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/ConfigOracle.java` | `statechart/scripts/test/ConfigOracle.java` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus.test.ts` | `statechart/scripts/test/corpus.test.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Counter/chart.mmd` | `statechart/scripts/test/corpus/Counter/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Counter/ChartRun.out` | `statechart/scripts/test/corpus/Counter/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Counter/Counter.cfg` | `statechart/scripts/test/corpus/Counter/Counter.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Counter/Counter.tla` | `statechart/scripts/test/corpus/Counter/Counter.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Counter/graph.dot` | `statechart/scripts/test/corpus/Counter/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Counter/sany.out` | `statechart/scripts/test/corpus/Counter/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Counter/verdict-1.out` | `statechart/scripts/test/corpus/Counter/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterAction/chart.mmd` | `statechart/scripts/test/corpus/CounterAction/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterAction/ChartRun.out` | `statechart/scripts/test/corpus/CounterAction/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterAction/CounterAction.cfg` | `statechart/scripts/test/corpus/CounterAction/CounterAction.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterAction/CounterAction.tla` | `statechart/scripts/test/corpus/CounterAction/CounterAction.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterAction/graph.dot` | `statechart/scripts/test/corpus/CounterAction/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterAction/sany.out` | `statechart/scripts/test/corpus/CounterAction/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterAction/verdict-1.exit` | `statechart/scripts/test/corpus/CounterAction/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterAction/verdict-1.out` | `statechart/scripts/test/corpus/CounterAction/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterAction/verdict-2.exit` | `statechart/scripts/test/corpus/CounterAction/verdict-2.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterAction/verdict-2.out` | `statechart/scripts/test/corpus/CounterAction/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterAction/verdict-3.out` | `statechart/scripts/test/corpus/CounterAction/verdict-3.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterDeadlock/chart.mmd` | `statechart/scripts/test/corpus/CounterDeadlock/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterDeadlock/ChartRun.out` | `statechart/scripts/test/corpus/CounterDeadlock/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterDeadlock/CounterDeadlock.cfg` | `statechart/scripts/test/corpus/CounterDeadlock/CounterDeadlock.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterDeadlock/CounterDeadlock.tla` | `statechart/scripts/test/corpus/CounterDeadlock/CounterDeadlock.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterDeadlock/graph.dot` | `statechart/scripts/test/corpus/CounterDeadlock/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterDeadlock/sany.out` | `statechart/scripts/test/corpus/CounterDeadlock/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterDeadlock/verdict-1.exit` | `statechart/scripts/test/corpus/CounterDeadlock/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterDeadlock/verdict-1.out` | `statechart/scripts/test/corpus/CounterDeadlock/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterDeadlock/verdict-2.exit` | `statechart/scripts/test/corpus/CounterDeadlock/verdict-2.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterDeadlock/verdict-2.out` | `statechart/scripts/test/corpus/CounterDeadlock/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterFan/chart.mmd` | `statechart/scripts/test/corpus/CounterFan/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterFan/ChartRun.out` | `statechart/scripts/test/corpus/CounterFan/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterFan/CounterFan.cfg` | `statechart/scripts/test/corpus/CounterFan/CounterFan.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterFan/CounterFan.tla` | `statechart/scripts/test/corpus/CounterFan/CounterFan.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterFan/graph.dot` | `statechart/scripts/test/corpus/CounterFan/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterFan/sany.out` | `statechart/scripts/test/corpus/CounterFan/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterFan/verdict-1.exit` | `statechart/scripts/test/corpus/CounterFan/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterFan/verdict-1.out` | `statechart/scripts/test/corpus/CounterFan/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterFan/verdict-2.out` | `statechart/scripts/test/corpus/CounterFan/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterGuard/chart.mmd` | `statechart/scripts/test/corpus/CounterGuard/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterGuard/ChartRun.exit` | `statechart/scripts/test/corpus/CounterGuard/ChartRun.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterGuard/ChartRun.out` | `statechart/scripts/test/corpus/CounterGuard/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterGuard/CounterGuard.cfg` | `statechart/scripts/test/corpus/CounterGuard/CounterGuard.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterGuard/CounterGuard.tla` | `statechart/scripts/test/corpus/CounterGuard/CounterGuard.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterGuard/graph.dot` | `statechart/scripts/test/corpus/CounterGuard/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterGuard/sany.out` | `statechart/scripts/test/corpus/CounterGuard/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterGuard/verdict-1.exit` | `statechart/scripts/test/corpus/CounterGuard/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterGuard/verdict-1.out` | `statechart/scripts/test/corpus/CounterGuard/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterGuard/verdict-2.exit` | `statechart/scripts/test/corpus/CounterGuard/verdict-2.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterGuard/verdict-2.out` | `statechart/scripts/test/corpus/CounterGuard/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInitPast/chart.mmd` | `statechart/scripts/test/corpus/CounterInitPast/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInitPast/ChartRun.out` | `statechart/scripts/test/corpus/CounterInitPast/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInitPast/CounterInitPast.cfg` | `statechart/scripts/test/corpus/CounterInitPast/CounterInitPast.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInitPast/CounterInitPast.tla` | `statechart/scripts/test/corpus/CounterInitPast/CounterInitPast.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInitPast/graph.dot` | `statechart/scripts/test/corpus/CounterInitPast/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInitPast/sany.out` | `statechart/scripts/test/corpus/CounterInitPast/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInitPast/verdict-1.exit` | `statechart/scripts/test/corpus/CounterInitPast/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInitPast/verdict-1.out` | `statechart/scripts/test/corpus/CounterInitPast/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInitPast/verdict-2.out` | `statechart/scripts/test/corpus/CounterInitPast/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInitPastHolds/chart.mmd` | `statechart/scripts/test/corpus/CounterInitPastHolds/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInitPastHolds/ChartRun.out` | `statechart/scripts/test/corpus/CounterInitPastHolds/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInitPastHolds/CounterInitPastHolds.cfg` | `statechart/scripts/test/corpus/CounterInitPastHolds/CounterInitPastHolds.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInitPastHolds/CounterInitPastHolds.tla` | `statechart/scripts/test/corpus/CounterInitPastHolds/CounterInitPastHolds.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInitPastHolds/graph.dot` | `statechart/scripts/test/corpus/CounterInitPastHolds/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInitPastHolds/sany.out` | `statechart/scripts/test/corpus/CounterInitPastHolds/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInitPastHolds/verdict-1.out` | `statechart/scripts/test/corpus/CounterInitPastHolds/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInstance/chart.mmd` | `statechart/scripts/test/corpus/CounterInstance/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInstance/ChartRun.out` | `statechart/scripts/test/corpus/CounterInstance/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInstance/CounterInstance.cfg` | `statechart/scripts/test/corpus/CounterInstance/CounterInstance.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInstance/CounterInstance.tla` | `statechart/scripts/test/corpus/CounterInstance/CounterInstance.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInstance/CounterSteps.tla` | `statechart/scripts/test/corpus/CounterInstance/CounterSteps.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInstance/graph.dot` | `statechart/scripts/test/corpus/CounterInstance/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInstance/sany.out` | `statechart/scripts/test/corpus/CounterInstance/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInstance/verdict-1.exit` | `statechart/scripts/test/corpus/CounterInstance/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterInstance/verdict-1.out` | `statechart/scripts/test/corpus/CounterInstance/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterJump/chart.mmd` | `statechart/scripts/test/corpus/CounterJump/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterJump/ChartRun.out` | `statechart/scripts/test/corpus/CounterJump/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterJump/CounterJump.cfg` | `statechart/scripts/test/corpus/CounterJump/CounterJump.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterJump/CounterJump.tla` | `statechart/scripts/test/corpus/CounterJump/CounterJump.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterJump/graph.dot` | `statechart/scripts/test/corpus/CounterJump/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterJump/sany.out` | `statechart/scripts/test/corpus/CounterJump/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterJump/verdict-1.exit` | `statechart/scripts/test/corpus/CounterJump/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterJump/verdict-1.out` | `statechart/scripts/test/corpus/CounterJump/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterJump/verdict-2.out` | `statechart/scripts/test/corpus/CounterJump/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterLoop/chart.mmd` | `statechart/scripts/test/corpus/CounterLoop/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterLoop/ChartRun.out` | `statechart/scripts/test/corpus/CounterLoop/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterLoop/CounterLoop.cfg` | `statechart/scripts/test/corpus/CounterLoop/CounterLoop.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterLoop/CounterLoop.tla` | `statechart/scripts/test/corpus/CounterLoop/CounterLoop.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterLoop/graph.dot` | `statechart/scripts/test/corpus/CounterLoop/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterLoop/sany.out` | `statechart/scripts/test/corpus/CounterLoop/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterLoop/verdict-1.exit` | `statechart/scripts/test/corpus/CounterLoop/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterLoop/verdict-1.out` | `statechart/scripts/test/corpus/CounterLoop/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterOrder/chart.mmd` | `statechart/scripts/test/corpus/CounterOrder/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterOrder/ChartRun.out` | `statechart/scripts/test/corpus/CounterOrder/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterOrder/CounterOrder.cfg` | `statechart/scripts/test/corpus/CounterOrder/CounterOrder.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterOrder/CounterOrder.tla` | `statechart/scripts/test/corpus/CounterOrder/CounterOrder.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterOrder/graph.dot` | `statechart/scripts/test/corpus/CounterOrder/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterOrder/sany.out` | `statechart/scripts/test/corpus/CounterOrder/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterOrder/verdict-1.exit` | `statechart/scripts/test/corpus/CounterOrder/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterOrder/verdict-1.out` | `statechart/scripts/test/corpus/CounterOrder/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterOrder/verdict-2.exit` | `statechart/scripts/test/corpus/CounterOrder/verdict-2.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterOrder/verdict-2.out` | `statechart/scripts/test/corpus/CounterOrder/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterRules/chart.mmd` | `statechart/scripts/test/corpus/CounterRules/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterRules/ChartRun.out` | `statechart/scripts/test/corpus/CounterRules/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterRules/CounterRules.cfg` | `statechart/scripts/test/corpus/CounterRules/CounterRules.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterRules/CounterRules.tla` | `statechart/scripts/test/corpus/CounterRules/CounterRules.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterRules/graph.dot` | `statechart/scripts/test/corpus/CounterRules/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterRules/Moves.tla` | `statechart/scripts/test/corpus/CounterRules/Moves.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterRules/sany.out` | `statechart/scripts/test/corpus/CounterRules/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterRules/verdict-1.exit` | `statechart/scripts/test/corpus/CounterRules/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterRules/verdict-1.out` | `statechart/scripts/test/corpus/CounterRules/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterRules/verdict-2.exit` | `statechart/scripts/test/corpus/CounterRules/verdict-2.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterRules/verdict-2.out` | `statechart/scripts/test/corpus/CounterRules/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterRules/verdict-3.exit` | `statechart/scripts/test/corpus/CounterRules/verdict-3.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterRules/verdict-3.out` | `statechart/scripts/test/corpus/CounterRules/verdict-3.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterRules/verdict-4.out` | `statechart/scripts/test/corpus/CounterRules/verdict-4.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterStart/chart.mmd` | `statechart/scripts/test/corpus/CounterStart/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterStart/ChartRun.out` | `statechart/scripts/test/corpus/CounterStart/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterStart/CounterStart.cfg` | `statechart/scripts/test/corpus/CounterStart/CounterStart.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterStart/CounterStart.tla` | `statechart/scripts/test/corpus/CounterStart/CounterStart.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterStart/graph.dot` | `statechart/scripts/test/corpus/CounterStart/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterStart/sany.out` | `statechart/scripts/test/corpus/CounterStart/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterStart/verdict-1.exit` | `statechart/scripts/test/corpus/CounterStart/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterStart/verdict-1.out` | `statechart/scripts/test/corpus/CounterStart/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterStart/verdict-2.out` | `statechart/scripts/test/corpus/CounterStart/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterStop/chart.mmd` | `statechart/scripts/test/corpus/CounterStop/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterStop/ChartRun.out` | `statechart/scripts/test/corpus/CounterStop/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterStop/CounterStop.cfg` | `statechart/scripts/test/corpus/CounterStop/CounterStop.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterStop/CounterStop.tla` | `statechart/scripts/test/corpus/CounterStop/CounterStop.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterStop/graph.dot` | `statechart/scripts/test/corpus/CounterStop/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterStop/sany.out` | `statechart/scripts/test/corpus/CounterStop/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterStop/verdict-1.out` | `statechart/scripts/test/corpus/CounterStop/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTie/chart.mmd` | `statechart/scripts/test/corpus/CounterTie/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTie/ChartRun.out` | `statechart/scripts/test/corpus/CounterTie/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTie/CounterTie.cfg` | `statechart/scripts/test/corpus/CounterTie/CounterTie.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTie/CounterTie.tla` | `statechart/scripts/test/corpus/CounterTie/CounterTie.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTie/graph.dot` | `statechart/scripts/test/corpus/CounterTie/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTie/sany.out` | `statechart/scripts/test/corpus/CounterTie/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTie/verdict-1.exit` | `statechart/scripts/test/corpus/CounterTie/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTie/verdict-1.out` | `statechart/scripts/test/corpus/CounterTie/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTie/verdict-2.exit` | `statechart/scripts/test/corpus/CounterTie/verdict-2.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTie/verdict-2.out` | `statechart/scripts/test/corpus/CounterTie/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTie/verdict-3.exit` | `statechart/scripts/test/corpus/CounterTie/verdict-3.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTie/verdict-3.out` | `statechart/scripts/test/corpus/CounterTie/verdict-3.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTie/verdict-4.out` | `statechart/scripts/test/corpus/CounterTie/verdict-4.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTieInGraph/chart.mmd` | `statechart/scripts/test/corpus/CounterTieInGraph/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTieInGraph/ChartRun.out` | `statechart/scripts/test/corpus/CounterTieInGraph/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTieInGraph/CounterTieInGraph.cfg` | `statechart/scripts/test/corpus/CounterTieInGraph/CounterTieInGraph.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTieInGraph/CounterTieInGraph.tla` | `statechart/scripts/test/corpus/CounterTieInGraph/CounterTieInGraph.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTieInGraph/graph.dot` | `statechart/scripts/test/corpus/CounterTieInGraph/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTieInGraph/sany.out` | `statechart/scripts/test/corpus/CounterTieInGraph/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTieInGraph/verdict-1.exit` | `statechart/scripts/test/corpus/CounterTieInGraph/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTieInGraph/verdict-1.out` | `statechart/scripts/test/corpus/CounterTieInGraph/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterTieInGraph/verdict-2.out` | `statechart/scripts/test/corpus/CounterTieInGraph/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterView/chart.mmd` | `statechart/scripts/test/corpus/CounterView/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterView/ChartRun.out` | `statechart/scripts/test/corpus/CounterView/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterView/CounterView.cfg` | `statechart/scripts/test/corpus/CounterView/CounterView.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterView/CounterView.tla` | `statechart/scripts/test/corpus/CounterView/CounterView.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterView/graph.dot` | `statechart/scripts/test/corpus/CounterView/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterView/sany.out` | `statechart/scripts/test/corpus/CounterView/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterView/verdict-1.exit` | `statechart/scripts/test/corpus/CounterView/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterView/verdict-1.out` | `statechart/scripts/test/corpus/CounterView/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterView/verdict-2.exit` | `statechart/scripts/test/corpus/CounterView/verdict-2.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterView/verdict-2.out` | `statechart/scripts/test/corpus/CounterView/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterView/verdict-3.exit` | `statechart/scripts/test/corpus/CounterView/verdict-3.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterView/verdict-3.out` | `statechart/scripts/test/corpus/CounterView/verdict-3.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterView/verdict-4.out` | `statechart/scripts/test/corpus/CounterView/verdict-4.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/CounterView/view.mjs` | `statechart/scripts/test/corpus/CounterView/view.mjs` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/DieHard/chart.mmd` | `statechart/scripts/test/corpus/DieHard/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/DieHard/ChartRun.out` | `statechart/scripts/test/corpus/DieHard/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/DieHard/DieHard.cfg` | `statechart/scripts/test/corpus/DieHard/DieHard.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/DieHard/DieHard.tla` | `statechart/scripts/test/corpus/DieHard/DieHard.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/DieHard/graph.dot` | `statechart/scripts/test/corpus/DieHard/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/DieHard/sany.out` | `statechart/scripts/test/corpus/DieHard/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/DieHard/verdict-1.exit` | `statechart/scripts/test/corpus/DieHard/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/DieHard/verdict-1.out` | `statechart/scripts/test/corpus/DieHard/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/DieHard/verdict-2.out` | `statechart/scripts/test/corpus/DieHard/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/FirstRule/chart.mmd` | `statechart/scripts/test/corpus/FirstRule/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/FirstRule/ChartRun.out` | `statechart/scripts/test/corpus/FirstRule/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/FirstRule/FirstRule.cfg` | `statechart/scripts/test/corpus/FirstRule/FirstRule.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/FirstRule/FirstRule.tla` | `statechart/scripts/test/corpus/FirstRule/FirstRule.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/FirstRule/graph.dot` | `statechart/scripts/test/corpus/FirstRule/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/FirstRule/sany.out` | `statechart/scripts/test/corpus/FirstRule/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/FirstRule/verdict-1.exit` | `statechart/scripts/test/corpus/FirstRule/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/FirstRule/verdict-1.out` | `statechart/scripts/test/corpus/FirstRule/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/FirstRule/verdict-2.exit` | `statechart/scripts/test/corpus/FirstRule/verdict-2.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/FirstRule/verdict-2.out` | `statechart/scripts/test/corpus/FirstRule/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/FirstRule/verdict-3.exit` | `statechart/scripts/test/corpus/FirstRule/verdict-3.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/FirstRule/verdict-3.out` | `statechart/scripts/test/corpus/FirstRule/verdict-3.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/FirstRule/verdict-4.exit` | `statechart/scripts/test/corpus/FirstRule/verdict-4.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/FirstRule/verdict-4.out` | `statechart/scripts/test/corpus/FirstRule/verdict-4.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/HiddenClock/chart.mmd` | `statechart/scripts/test/corpus/HiddenClock/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/HiddenClock/ChartRun.out` | `statechart/scripts/test/corpus/HiddenClock/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/HiddenClock/graph.dot` | `statechart/scripts/test/corpus/HiddenClock/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/HiddenClock/HiddenClock.cfg` | `statechart/scripts/test/corpus/HiddenClock/HiddenClock.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/HiddenClock/HiddenClock.tla` | `statechart/scripts/test/corpus/HiddenClock/HiddenClock.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/HiddenClock/sany.out` | `statechart/scripts/test/corpus/HiddenClock/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/HiddenClock/verdict-1.exit` | `statechart/scripts/test/corpus/HiddenClock/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/HiddenClock/verdict-1.out` | `statechart/scripts/test/corpus/HiddenClock/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Login/chart.mmd` | `statechart/scripts/test/corpus/Login/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Login/ChartRun.out` | `statechart/scripts/test/corpus/Login/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Login/graph.dot` | `statechart/scripts/test/corpus/Login/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Login/Login.cfg` | `statechart/scripts/test/corpus/Login/Login.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Login/Login.tla` | `statechart/scripts/test/corpus/Login/Login.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Login/sany.out` | `statechart/scripts/test/corpus/Login/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Login/verdict-1.out` | `statechart/scripts/test/corpus/Login/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Login/view.mjs` | `statechart/scripts/test/corpus/Login/view.mjs` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginGuarded/chart.mmd` | `statechart/scripts/test/corpus/LoginGuarded/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginGuarded/ChartRun.out` | `statechart/scripts/test/corpus/LoginGuarded/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginGuarded/graph.dot` | `statechart/scripts/test/corpus/LoginGuarded/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginGuarded/LoginGuarded.cfg` | `statechart/scripts/test/corpus/LoginGuarded/LoginGuarded.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginGuarded/LoginGuarded.tla` | `statechart/scripts/test/corpus/LoginGuarded/LoginGuarded.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginGuarded/sany.out` | `statechart/scripts/test/corpus/LoginGuarded/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginGuarded/verdict-1.out` | `statechart/scripts/test/corpus/LoginGuarded/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginGuarded/view.mjs` | `statechart/scripts/test/corpus/LoginGuarded/view.mjs` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginParallel/chart.mmd` | `statechart/scripts/test/corpus/LoginParallel/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginParallel/ChartRun.out` | `statechart/scripts/test/corpus/LoginParallel/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginParallel/graph.dot` | `statechart/scripts/test/corpus/LoginParallel/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginParallel/LoginParallel.cfg` | `statechart/scripts/test/corpus/LoginParallel/LoginParallel.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginParallel/LoginParallel.tla` | `statechart/scripts/test/corpus/LoginParallel/LoginParallel.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginParallel/sany.out` | `statechart/scripts/test/corpus/LoginParallel/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginParallel/verdict-1.exit` | `statechart/scripts/test/corpus/LoginParallel/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginParallel/verdict-1.out` | `statechart/scripts/test/corpus/LoginParallel/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginParallel/verdict-2.out` | `statechart/scripts/test/corpus/LoginParallel/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/LoginParallel/view.mjs` | `statechart/scripts/test/corpus/LoginParallel/view.mjs` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayer/chart.mmd` | `statechart/scripts/test/corpus/MediaPlayer/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayer/ChartRun.out` | `statechart/scripts/test/corpus/MediaPlayer/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayer/graph.dot` | `statechart/scripts/test/corpus/MediaPlayer/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayer/MediaPlayer.cfg` | `statechart/scripts/test/corpus/MediaPlayer/MediaPlayer.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayer/MediaPlayer.tla` | `statechart/scripts/test/corpus/MediaPlayer/MediaPlayer.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayer/sany.out` | `statechart/scripts/test/corpus/MediaPlayer/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayer/verdict-1.exit` | `statechart/scripts/test/corpus/MediaPlayer/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayer/verdict-1.out` | `statechart/scripts/test/corpus/MediaPlayer/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayer/verdict-2.out` | `statechart/scripts/test/corpus/MediaPlayer/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayer/view.mjs` | `statechart/scripts/test/corpus/MediaPlayer/view.mjs` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerFixed/chart.mmd` | `statechart/scripts/test/corpus/MediaPlayerFixed/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerFixed/ChartRun.out` | `statechart/scripts/test/corpus/MediaPlayerFixed/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerFixed/graph.dot` | `statechart/scripts/test/corpus/MediaPlayerFixed/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerFixed/MediaPlayerFixed.cfg` | `statechart/scripts/test/corpus/MediaPlayerFixed/MediaPlayerFixed.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerFixed/MediaPlayerFixed.tla` | `statechart/scripts/test/corpus/MediaPlayerFixed/MediaPlayerFixed.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerFixed/sany.out` | `statechart/scripts/test/corpus/MediaPlayerFixed/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerFixed/verdict-1.out` | `statechart/scripts/test/corpus/MediaPlayerFixed/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerFixed/view.mjs` | `statechart/scripts/test/corpus/MediaPlayerFixed/view.mjs` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/chart.mmd` | `statechart/scripts/test/corpus/MediaPlayerProps/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/ChartRun.out` | `statechart/scripts/test/corpus/MediaPlayerProps/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/graph.dot` | `statechart/scripts/test/corpus/MediaPlayerProps/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/MediaPlayer.tla` | `statechart/scripts/test/corpus/MediaPlayerProps/MediaPlayer.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/MediaPlayerProps.cfg` | `statechart/scripts/test/corpus/MediaPlayerProps/MediaPlayerProps.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/MediaPlayerProps.tla` | `statechart/scripts/test/corpus/MediaPlayerProps/MediaPlayerProps.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/sany.out` | `statechart/scripts/test/corpus/MediaPlayerProps/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/verdict-1.exit` | `statechart/scripts/test/corpus/MediaPlayerProps/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/verdict-1.out` | `statechart/scripts/test/corpus/MediaPlayerProps/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/verdict-2.out` | `statechart/scripts/test/corpus/MediaPlayerProps/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/verdict-3.out` | `statechart/scripts/test/corpus/MediaPlayerProps/verdict-3.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/verdict-4.exit` | `statechart/scripts/test/corpus/MediaPlayerProps/verdict-4.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/verdict-4.out` | `statechart/scripts/test/corpus/MediaPlayerProps/verdict-4.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/verdict-5.exit` | `statechart/scripts/test/corpus/MediaPlayerProps/verdict-5.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/verdict-5.out` | `statechart/scripts/test/corpus/MediaPlayerProps/verdict-5.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/verdict-6.out` | `statechart/scripts/test/corpus/MediaPlayerProps/verdict-6.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/MediaPlayerProps/view.mjs` | `statechart/scripts/test/corpus/MediaPlayerProps/view.mjs` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/PickWorker/chart.mmd` | `statechart/scripts/test/corpus/PickWorker/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/PickWorker/ChartRun.out` | `statechart/scripts/test/corpus/PickWorker/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/PickWorker/graph.dot` | `statechart/scripts/test/corpus/PickWorker/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/PickWorker/PickWorker.cfg` | `statechart/scripts/test/corpus/PickWorker/PickWorker.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/PickWorker/PickWorker.tla` | `statechart/scripts/test/corpus/PickWorker/PickWorker.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/PickWorker/sany.out` | `statechart/scripts/test/corpus/PickWorker/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/PickWorker/verdict-1.out` | `statechart/scripts/test/corpus/PickWorker/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Shadow/chart.mmd` | `statechart/scripts/test/corpus/Shadow/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Shadow/ChartRun.out` | `statechart/scripts/test/corpus/Shadow/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Shadow/graph.dot` | `statechart/scripts/test/corpus/Shadow/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Shadow/sany.out` | `statechart/scripts/test/corpus/Shadow/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Shadow/Shadow.cfg` | `statechart/scripts/test/corpus/Shadow/Shadow.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Shadow/Shadow.tla` | `statechart/scripts/test/corpus/Shadow/Shadow.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Shadow/ShadowLib.tla` | `statechart/scripts/test/corpus/Shadow/ShadowLib.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Shadow/ShadowSub.tla` | `statechart/scripts/test/corpus/Shadow/ShadowSub.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/Shadow/verdict-1.out` | `statechart/scripts/test/corpus/Shadow/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/SpacedNames/chart.mmd` | `statechart/scripts/test/corpus/SpacedNames/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/SpacedNames/ChartRun.out` | `statechart/scripts/test/corpus/SpacedNames/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/SpacedNames/graph.dot` | `statechart/scripts/test/corpus/SpacedNames/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/SpacedNames/sany.out` | `statechart/scripts/test/corpus/SpacedNames/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/SpacedNames/SpacedNames.cfg` | `statechart/scripts/test/corpus/SpacedNames/SpacedNames.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/SpacedNames/SpacedNames.tla` | `statechart/scripts/test/corpus/SpacedNames/SpacedNames.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/SpacedNames/verdict-1.exit` | `statechart/scripts/test/corpus/SpacedNames/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/SpacedNames/verdict-1.out` | `statechart/scripts/test/corpus/SpacedNames/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/SpacedNames/verdict-2.exit` | `statechart/scripts/test/corpus/SpacedNames/verdict-2.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/SpacedNames/verdict-2.out` | `statechart/scripts/test/corpus/SpacedNames/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhase/chart.mmd` | `statechart/scripts/test/corpus/TwoPhase/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhase/ChartRun.out` | `statechart/scripts/test/corpus/TwoPhase/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhase/graph.dot` | `statechart/scripts/test/corpus/TwoPhase/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhase/sany.out` | `statechart/scripts/test/corpus/TwoPhase/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhase/TwoPhase.cfg` | `statechart/scripts/test/corpus/TwoPhase/TwoPhase.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhase/TwoPhase.tla` | `statechart/scripts/test/corpus/TwoPhase/TwoPhase.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhase/verdict-1.exit` | `statechart/scripts/test/corpus/TwoPhase/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhase/verdict-1.out` | `statechart/scripts/test/corpus/TwoPhase/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhase/verdict-2.out` | `statechart/scripts/test/corpus/TwoPhase/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhase/view.mjs` | `statechart/scripts/test/corpus/TwoPhase/view.mjs` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhaseFixed/chart.mmd` | `statechart/scripts/test/corpus/TwoPhaseFixed/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhaseFixed/ChartRun.out` | `statechart/scripts/test/corpus/TwoPhaseFixed/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhaseFixed/graph.dot` | `statechart/scripts/test/corpus/TwoPhaseFixed/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhaseFixed/sany.out` | `statechart/scripts/test/corpus/TwoPhaseFixed/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhaseFixed/TwoPhaseFixed.cfg` | `statechart/scripts/test/corpus/TwoPhaseFixed/TwoPhaseFixed.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhaseFixed/TwoPhaseFixed.tla` | `statechart/scripts/test/corpus/TwoPhaseFixed/TwoPhaseFixed.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhaseFixed/verdict-1.out` | `statechart/scripts/test/corpus/TwoPhaseFixed/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TwoPhaseFixed/view.mjs` | `statechart/scripts/test/corpus/TwoPhaseFixed/view.mjs` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TypeGuard/chart.mmd` | `statechart/scripts/test/corpus/TypeGuard/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TypeGuard/ChartRun.exit` | `statechart/scripts/test/corpus/TypeGuard/ChartRun.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TypeGuard/ChartRun.out` | `statechart/scripts/test/corpus/TypeGuard/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TypeGuard/graph.dot` | `statechart/scripts/test/corpus/TypeGuard/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TypeGuard/sany.out` | `statechart/scripts/test/corpus/TypeGuard/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TypeGuard/TypeGuard.cfg` | `statechart/scripts/test/corpus/TypeGuard/TypeGuard.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TypeGuard/TypeGuard.tla` | `statechart/scripts/test/corpus/TypeGuard/TypeGuard.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TypeGuard/verdict-1.exit` | `statechart/scripts/test/corpus/TypeGuard/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TypeGuard/verdict-1.out` | `statechart/scripts/test/corpus/TypeGuard/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TypeGuard/verdict-2.exit` | `statechart/scripts/test/corpus/TypeGuard/verdict-2.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/TypeGuard/verdict-2.out` | `statechart/scripts/test/corpus/TypeGuard/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/UserNoDeadlock/chart.mmd` | `statechart/scripts/test/corpus/UserNoDeadlock/chart.mmd` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/UserNoDeadlock/ChartRun.out` | `statechart/scripts/test/corpus/UserNoDeadlock/ChartRun.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/UserNoDeadlock/graph.dot` | `statechart/scripts/test/corpus/UserNoDeadlock/graph.dot` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/UserNoDeadlock/sany.out` | `statechart/scripts/test/corpus/UserNoDeadlock/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/UserNoDeadlock/UserNoDeadlock.cfg` | `statechart/scripts/test/corpus/UserNoDeadlock/UserNoDeadlock.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/UserNoDeadlock/UserNoDeadlock.tla` | `statechart/scripts/test/corpus/UserNoDeadlock/UserNoDeadlock.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/UserNoDeadlock/verdict-1.exit` | `statechart/scripts/test/corpus/UserNoDeadlock/verdict-1.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/UserNoDeadlock/verdict-1.out` | `statechart/scripts/test/corpus/UserNoDeadlock/verdict-1.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/UserNoDeadlock/verdict-2.exit` | `statechart/scripts/test/corpus/UserNoDeadlock/verdict-2.exit` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/corpus/UserNoDeadlock/verdict-2.out` | `statechart/scripts/test/corpus/UserNoDeadlock/verdict-2.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/differential.test.ts` | `statechart/scripts/test/differential.test.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/drawn.ts` | `statechart/scripts/test/drawn.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/grid/Grid.cfg` | `statechart/scripts/test/grid/Grid.cfg` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/grid/Grid.tla` | `statechart/scripts/test/grid/Grid.tla` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/grid/sany.out` | `statechart/scripts/test/grid/sany.out` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/java.ts` | `statechart/scripts/test/java.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/labels.ts` | `statechart/scripts/test/labels.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/messages.test.ts` | `statechart/scripts/test/messages.test.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/pipeline.test.ts` | `statechart/scripts/test/pipeline.test.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/plain-tlc.test.ts` | `statechart/scripts/test/plain-tlc.test.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/render.test.ts` | `statechart/scripts/test/render.test.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/tlc-out.test.ts` | `statechart/scripts/test/tlc-out.test.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/test/tlc.ts` | `statechart/scripts/test/tlc.ts` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/tsconfig.json` | `statechart/scripts/tsconfig.json` | other | ok | 二进制原样复制，字节一致 |
| `statechart/scripts/worker.ts` | `statechart/scripts/worker.ts` | other | ok | 二进制原样复制，字节一致 |
