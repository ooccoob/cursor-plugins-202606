# Bugbot 分诊

当 Babysit 手册（`../playbooks/babysit.md`）处理 Bugbot 或评审自动化评论时，使用这份参考。目标不是默认忽略 Bugbot。目标是不要再把每条评论都当成必须修改代码。

## 判定标准

行动之前，先给每个 Bugbot 线程分类：

- `fix`：评论指出的是可信的正确性、安全、隐私、数据丢失、认证、计费、迁移、幂等性、竞态或已交付行为问题。在最低的属主 PR 中修复，然后回复提交 SHA 并解决该线程。
- `dismiss`：评论符合已记录的低风险噪声模式，且当前代码/上下文证明该疑虑不需要改代码。回复简短理由并解决该线程。
- `ask`：评论新颖、严重级别高、涉及安全/隐私/数据，或含糊不清。去问用户，而不是猜。

拿不准时就问。跳过一条噪声型代码质量评论代价很低；跳过真实的数据或安全缺陷代价不是。

## 经验模式格式

按下面的形状添加未来的模式：

```markdown
### <short pattern name>

- Confidence: candidate | recurring | strong
- Skip when: <conditions that must be true>
- Do not skip when: <risk boundaries>
- Example signal: <phrases or code context that identify the pattern>
- Source: <PR/comment URL or short historical note>
```

一个或两个例子用 `candidate`。多次真实驳回之后用 `recurring`。只有当模式狭窄、反复验证且低风险时才用 `strong`。

## 常见的可跳过候选

### 有意的 UI 或设计系统视觉改动

- 置信度：candidate
- 满足以下条件时跳过：PR 描述、截图、设计评审或附近代码明确说明了该视觉改动，而 Bugbot 评论只是在重述某个共享视觉默认值变了。
- 以下情况不跳过：评论指向无障碍、焦点可见性、键盘导航、颜色对比度，或 PR 并未有意改动的组件 API 契约。
- Example signal: 关于焦点轮廓、按钮尺寸、间距或共享组件视觉默认值的评论，而属主回复"intentional"或"intended"。

### Bugbot 看不到的上层堆叠或堆叠内局部用法

- 置信度：candidate
- 满足以下条件时跳过：Bugbot 把某个导出、组件、辅助函数或文件标为未使用，而当前所用 forge 的 PR 列表与 diff、上层堆叠的 diff 或 PR 上下文显示它被堆叠中更靠后的 PR 使用。
- 以下情况不跳过：当前 PR 不属于任何堆叠、该符号是公开 API，或所谓上层用法无法核实。
- Example signal: "Exported component is never used"，人类回复类似"used upstack"。

### 并行实现期间的临时重复

- 置信度：candidate
- 满足以下条件时跳过：PR 有意重复少量代码，以便让一条新路径与一条正在被删除、替换或验证的旧路径并行存在。
- 以下情况不跳过：重复的代码改变了安全、计费、数据访问、API 行为，或一个长期存在的共享抽象明显能降低风险。
- Example signal: "Significant duplication"或"duplicated validation logic"，而属主说明旧路径将被删除，或重复逻辑是有意局部的。

### 既有框架或组件不变量已覆盖该告警

- 置信度：candidate
- 满足以下条件时跳过：该疑虑已由共享组件、框架契约、类型不变量，或当前 diff 与附近代码中可见的单一事实来源保证。
- 以下情况不跳过：该不变量只是被假设而非被强制、依赖时序，或跨越异步/状态边界而值可能发散。
- Example signal: 关于内层 popover 缺少 max-height 的评论，而共享 popover 已强制视口边界；或可空值场景中，本地被检查的值与传入的值来自同一来源。

### 属主声明的后续工作或推迟的清理

- 置信度：candidate
- 满足以下条件时跳过：PR 属主明确说该问题是已知的后续工作、当前 PR 没有使该行为变差，且评论不涉及高风险领域。
- 以下情况不跳过：智能体在缺少属主输入的情况下行动、该问题属于中/高严重级别的产品行为，或推迟会合入一个新的回归。
- Example signal: "I'll worry about that later"或"we'll delete this eventually"。

### 自我撤回或明确误报的规则评论

- 置信度：recurring
- 满足以下条件时跳过：评论正文或 Bugbot 后续回复明确说该发现已撤回、已合规或属于误报，且智能体能在本地核实相关规则。
- 以下情况不跳过：唯一证据是某人在高风险问题上说了"false positive"而没有任何解释。
- Example signal: 一条文件命名规则评论，其正文说该文件已合规。

## 默认要问的类别

即使之前的 PR 驳回过类似问题，也不要自动跳过这些类别：

- 安全、隐私、认证、计费、数据保留、训练数据与权限边界方面的发现。
- 高严重级别的发现。
- 迁移、schema、幂等性、并发与跨系统行为方面的发现。
- 建议的修复很小、明显降低风险且不改变产品意图的评论。

历史数据表明，人类有时会驳回安全/数据流相关的评论。把那些当作属主的判断，而不是全团队通用的跳过规则。

## 近期盯守中得到的候选经验

在盯守期间或之后，把看起来对团队有用但尚不成熟的候选经验追加到这里。一旦多个 PR 确认了某个模式，优先把反复出现的候选提升到上一节。

### 手工重新实现浏览器原生行为

- 置信度：candidate
- 满足以下条件时跳过：几乎永远不要跳过。当 diff 用等价的手工实现替换浏览器原生行为（原生 sticky → JS 定位的克隆、原生滚动定位 → 转发的 wheel/touch 事件、paint-order 遮挡 → mask/clip-path），Bugbot 针对这类代码提出的逻辑缺陷发现一直都是有道理的。
- 以下情况不跳过：该发现涉及这类代码里的事件转发缺口（wheel deltaMode、触摸平移、边缘处的滚动链、tap slop）、mask/clip 命中测试偏差，或 observer 与 React 状态之间的时序竞态。默认修复。
- Example signal: "masks do not affect hit-testing"、"overlay blocks wheel scroll"、"ignores deltaMode"、"runs in the IntersectionObserver callback before React applies state"。
- Source: 一个 sticky 遮挡 PR：六轮 Bugbot，约十八条发现，每一条都修复而非驳回。

### 契约测试漂移的说法很容易核实——先跑测试

- 置信度：candidate
- 满足以下条件时跳过：绝不跳过核实本身；它只花一条命令。当一个 PR
  交付了钉住协议或文档文字的契约测试（对 SKILL.md 跑正则、快照文档措辞），
  而 Bugbot 声称"测试已与文档不符"（或反之），先在该 PR tip 上跑这个测试，
  再做分类。跑红就在实证上确认了该说法；跑绿则是驳回回复里
  具体的反证。
- 以下情况不跳过：不适用——这是核实的捷径，不是驳回模式。
  注意，重复轮次偏向驳回的启发式在这里会误判：
  钉住文字的测试之所以漂移，正是因为先前的修复轮次改动了那段文字。
- Example signal: 某个 PR 上出现"Contract test omits the pre-fix wait"，而该 PR 更早的
  修复提交重写了被钉住的那段文字；在 tip 上跑该测试，
  恰好在所引断言处失败。
- Source: 一个钉住文字的 PR，八轮 Bugbot；该说法在第 7 轮是真实的，
  尽管之前每一轮都已被修复并解决。

### 同一 PR 中更晚已修复的过期安全评审发现

- 置信度：candidate
- 满足以下条件时跳过：某次智能体安全评审（或类似机制）声称缺少某个授权/校验调用，而当前 PR tip 明显包含该确切的关卡（含测试），通常是在评审运行之后的一个加固提交里加入的。
- 以下情况不跳过：所引辅助函数对当前讨论的主体是空操作、该检查在它所守护的副作用之后运行，或对所述主体的覆盖缺失。
- Example signal: 一条 HIGH 级别的"missing authorization check"发现，而该确切的守卫在 tip 上已先于副作用被调用。
- Source: 一个 webhook 端点 PR，其加固提交晚于该次评审运行。

### 放宽一个刻意收窄的错误条件会掩盖真正的错误

- 置信度：candidate
- 满足以下条件时跳过：该发现要求把收窄的错误条件（某个特定的
  `errno`、错误码或状态类别）放宽为全捕获，而这份收窄
  编码了真实的区别。典型形状是以 `ENOENT` 为条件的依赖回退：
  "二进制未安装"与"命令跑了但失败"是两种不同情况。
  对任何非零退出都重试，会把一次合法失败（未找到、认证过期、
  网络）重跑到回退路径上，然后报告回退的错误，掩盖真正的那个。
- 以下情况不跳过：收窄的条件漏掉了同一类别中的某种情况
  （另一个"二进制不可用"的 errno 如 `EACCES`、另一种传输层
  失败）、未处理的路径会丢数据或留下部分状态，或重试
  是幂等的**且**原始错误仍被呈现。
- Example signal: "only retries when X fails with ENOENT … never tries the
  fallback even when a working Y exists"，指向的代码其回退是为
  缺失依赖而存在，而不是为失败的操作。
- Source: 一个 CLI 重命名 PR，其回退是为缺失的二进制而存在，
  而不是为失败的命令。
