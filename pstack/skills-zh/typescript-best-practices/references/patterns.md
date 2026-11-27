# TypeScript 模式

`SKILL.md` 中每条规则的代码示例。其底层原则与语言无关。参见 **type-system-discipline** 和 **boundary-discipline** 原则 Skill。

## 品牌类型

为原始类型打上品牌，使它们不会被混用。在边界处校验一次。下游代码信任该类型。

```ts
type AgentId = string & { readonly __brand: "AgentId" };

function isAgentId(input: string): input is AgentId {
  return isUUID(input);
}

function parseAgentId(input: string): AgentId {
  if (!isAgentId(input)) throw new Error(`Invalid agent id: ${input}`);
  return input;
}

function focusAgent(id: AgentId): void {
  /* 输入是可信的 */
}
```

沿用 `readonly __brand: 'X'` 这一形状。不要另发明新约定。

## 可辨识联合

用字面量判别字段建模各变体。每个变体共用该字段名，且每个变体的值唯一，因此不可能的组合无法被表示。

```ts
// 不要这样做。布尔值加可选字段会允许矛盾状态存在。
type DiffState = { loading: boolean; diff?: GitDiff; error?: string };

// 要这样做。只存在合法状态。
type DiffState =
  | { kind: "loading" }
  | { kind: "ready"; diff: GitDiff }
  | { kind: "error"; error: string };
```

选定一个判别字段名（`kind`、`type`、`tag`）并坚持使用。

## 构造式建模

用全部合法的部件构造类型，而不是用运行时检查去限制一个松散类型。

非空，通过变长元组：

```ts
type NonEmpty<T> = [T, ...T[]];

// 不要这样做：T[] 加上每个调用方都必须重复的长度检查
function pickWinner(entries: string[]): string {
  if (entries.length === 0) throw new Error("no entries");
  return entries[Math.floor(Math.random() * entries.length)];
}

// 要这样做：该类型的空值无法存在
function pickWinner(entries: NonEmpty<string>): string {
  return entries[Math.floor(Math.random() * entries.length)];
}
```

当传入的是普通 `T[]` 时，用守卫收窄一次。这一事实随后随类型一起传递：

```ts
const isNonEmpty = <T>(arr: T[]): arr is NonEmpty<T> => arr.length > 0;
```

偶数长度，用对：

```ts
type Pairs<T> = [T, T][];
```

时间区间，用起点加时长：

```ts
// 不要这样做：靠注释承载不变式
type TimeRange = { start: Date; end: Date }; // start <= end

// 要这样做：负区间无法被写出；需要时推导出 end
type TimeRange = { start: Date; durationMs: number };
```

让 `durationMs` 保持普通数字。只有当原始数字可能被传入期望时长之处时才给它打品牌（见品牌类型一节），不要条件反射地打品牌。选择能让坏状态无法构造的表示，然后在上面暴露你需要的读取方式（`pairs.flat()`、`rangeEnd()` 辅助函数）。

## 最简单的全函数类型

不要把所有东西都收紧。当对 `T[]` 的每个操作都是全函数时，就保留 `T[]`：

```ts
const sum = (xs: number[]) => xs.reduce((a, b) => a + b, 0); // [] 得到 0，没问题
```

当松散类型在使用处迫使你说谎时才收紧。征兆是 `!`、`arr[0] as T`，以及"永不发生"的抛出：

```ts
// 不要这样做：把部分性偷带过编译器
function newestSession(sessions: Session[]): Session {
  return sessions.at(0)!;
}

// 要这样做：收紧输入，断言就消失了
function newestSession(sessions: NonEmpty<Session>): Session {
  return sessions[0];
}
```

把返回值放宽为 `Session | undefined` 是另一种全函数签名。

## 用 `unknown` 而非 `any`

外部数据始终是 `unknown`。使用前先收窄。

```ts
// 不要这样做
function handle(input: any) {
  return input.foo.bar;
}

// 要这样做
function handle(input: unknown) {
  if (typeof input === "object" && input !== null && "foo" in input) {
    // 已收窄；编译器验证访问
  }
}
```

外部来源包括 RPC 负载、`JSON.parse`、`postMessage`、IPC、文件内容、环境变量、数据库结果。

## 模式优先于手写守卫

在为外部数据编写逐属性类型守卫之前，先寻找仓库的运行时 schema 库和已有 schema。让一个 schema 独占校验职责，并从它派生出 TypeScript 类型。不要同时维护一个 schema、一个重复的 interface 和一个可能与之漂移的守卫。

```ts
import { z } from "zod";

const UserSchema = z.object({
  id: z.string().uuid(),
  role: z.enum(["admin", "member"]),
});

type User = z.infer<typeof UserSchema>;

function parseUser(input: unknown): User {
  return UserSchema.parse(input);
}
```

当失败是预期分支时使用 `safeParse`。当仓库使用其他 schema 库时，使用等价的推断辅助函数。不要为一个守卫新增 schema 依赖。这条规则优先采用代码库已经信任的 schema 体系。

## 禁止 `as` 类型断言

每个 `as` 都是一次潜在的运行时崩溃。只应在类型系统已校验断言之后才使用。

```ts
import { z } from "zod";

// 不要这样做
const user = data as User;

// 不要这样做
function isUser(data: unknown): data is User {
  return typeof data === "object" && data !== null && "id" in data;
}

// 要这样做
const userSchema = z.object({ id: z.string(), name: z.string() });
type User = z.infer<typeof userSchema>;

function parseUser(data: unknown): User {
  return userSchema.parse(data);
}
```

当类型先于校验器存在时，用该类型标注校验器。编译器随后会拒绝证明力弱于该类型的校验器。把下面对象中的 `name` 去掉，赋值就无法编译。

```ts
type User = { id: string; name: string };

const userSchema: z.ZodType<User> = z.object({ id: z.string(), name: z.string() });
```

在既有代码中重构掉一个 `as` 时，先判断 TypeScript 为什么无法推断：

- 缺少判别字段：加上一个，改用可辨识联合。
- 源类型过宽（例如 `Record<string, unknown>`）：收窄它。
- 边界未加类型：用拥有该形状的 schema 解析。只在该形状尚无 schema 时才新增 schema。
- 确实无法表达：使用品牌类型或 `satisfies`。

## 类型收窄层级

从最优到最后的退路：

1. **可辨识联合的 switch / if。** 编译器自动收窄。
2. **`in` 运算符。** `"key" in obj` 收窄到包含该键的变体。
3. **`typeof` / `instanceof`。** 用于原始类型和类实例。
4. **用户定义类型守卫。** 当以上都不够用时。
5. **`as` 类型断言。** 仅在校验之后。

```ts
function area(s: Shape): number {
  if ("radius" in s) return Math.PI * s.radius ** 2; // 收窄为 circle
  return s.width * s.height; // 收窄为 rect
}
```

## 类型守卫

守卫必须真正验证其断言。说谎的守卫比 `as` 更糟。

```ts
function isCircle(s: Shape): s is Shape & { kind: "circle" } {
  return s.kind === "circle";
}
```

在可能的情况下优先使用判别字段收窄。

## 穷尽性

在 default 分支中，把判别字段赋给一个 `never` 类型的局部变量。

```ts
// 有返回值的 switch
function area(s: Shape): number {
  switch (s.kind) {
    case "circle":
      return Math.PI * s.radius ** 2;
    case "rect":
      return s.width * s.height;
    default: {
      const _exhaustive: never = s;
      return _exhaustive;
    }
  }
}

// 无返回值的 switch
function handle(s: Shape): void {
  switch (s.kind) {
    case "circle":
      drawCircle(s);
      break;
    case "rect":
      drawRect(s);
      break;
    default: {
      const _exhaustive: never = s;
      void _exhaustive;
    }
  }
}
```

有返回值的 switch 用 return 风格，语句型 switch 用 void 风格。

## `satisfies` 优先于 `as`

`satisfies` 在不放宽字面量类型的前提下完成校验。

```ts
// 不要这样做。会放宽并丢失字面量类型。
const config = { theme: "dark", cols: 3 } as Config;

// 要这样做。既校验又保留字面量类型。
const config = { theme: "dark", cols: 3 } satisfies Config;
// config.theme 是 "dark"（字面量），不是 string
```

## 边界校验

在数据进入处校验一次。内部信任类型。参见 **boundary-discipline** 原则 Skill。

- **传输格式**（proto、JSON-RPC）：用 `ignoreUnknownFields` 解析，使向前兼容的变更不会破坏旧客户端。
- **持久化 JSON：** 带版本号的 blob，在解析处包 try/catch。
- **不要重复校验**：调用链深处不再校验。

## 从 schema 派生类型

当 `.proto`、OpenAPI 规范、GraphQL schema 或数据库迁移已经定义好某个形状时，从生成的类型派生，而不是重复定义。

```ts
// 不要这样做。重复形状，schema 变化时会漂移。
type CheckSummary = {
  totalCount: number;
  checks: { name: string; status: string }[];
};
function renderChecks(s: CheckSummary) {
  /* ... */
}

// 要这样做。从生成的 schema 类型派生。
import type { ChecksMessage } from "<generated module>";
function renderChecks(s: Pick<ChecksMessage, "totalCount" | "checks">) {
  /* ... */
}
```

在编写新 interface 之前，先用 `Pick`、`Omit`、`Parameters`、`ReturnType`、`Awaited`、`typeof`。

## 对象参数

```ts
// 不要这样做。交换两个参数后仍然能编译。
openFile(uri, {
  startLineNumber: 10,
  startColumn: 1,
  endLineNumber: 10,
  endColumn: 1,
});

// 要这样做。与顺序无关，自解释。
openFile({
  uri,
  selection: {
    startLineNumber: 10,
    startColumn: 1,
    endLineNumber: 10,
    endColumn: 1,
  },
});
```

热路径上除外：逐帧渲染、分词器、解析器，以及任何分配开销重要的紧凑循环。