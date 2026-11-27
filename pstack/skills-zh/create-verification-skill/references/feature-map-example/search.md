# 搜索笔记

Search 让用户按标题或正文文本查找笔记、查看命中的笔记，并区分“没有匹配”与“搜索不可用”。

## Sub-features

- `search-open` 从每个受支持的浏览器入口点打开搜索。
- `search-match` 返回标题和正文的命中结果，且不改变笔记数据。
- `search-open-result` 在笔记编辑器中打开某条结果。
- `search-empty` 对无匹配的查询显示完整的空态。
- `search-clear` 清除查询并恢复最近笔记视图。
- `search-cli` 从终端返回相同的命中笔记。

## How to get to it (user POV)

- 在浏览器工具栏选择 `Search` 按钮。
- 当焦点不在可编辑字段内时，在浏览器中按 `/`。
- 在终端运行 `notes search <query>`。

## Driving it with control-notes

Preconditions:

- Notes 在 `http://127.0.0.1:4173` 健康运行。
- 一次性数据目录中包含 `Quarterly plan`，其正文为 `Draft budget`。
- `control-notes doctor` 报告预期的 URL 和数据目录。

- **工具栏入口。** 选择 `Search` 按钮。运行 `control-notes browser click --role button --name "Search"`。出现名为 `Search notes` 的对话框，焦点位于其搜索框。
- **键盘入口。** 关闭对话框，让页面获得焦点，然后按 `/`。运行 `control-notes browser press --key "/"`。同一个对话框出现，且页面没有插入斜杠。
- **标题命中。** 输入 `quarterly`。运行 `control-notes browser fill --role searchbox --name "Search notes" --value "quarterly"`。`Search results` 列表包含 `Quarterly plan`，且不包含 `Grocery list`。
- **正文命中。** 把查询替换为 `budget`。运行 `control-notes browser fill --role searchbox --name "Search notes" --value "budget"`。结果 `Quarterly plan` 仍然可见，并带有正文命中摘录。
- **打开结果。** 选择 `Quarterly plan`。运行 `control-notes browser click --role link --name "Quarterly plan"`。对话框关闭，编辑器标题显示为 `Quarterly plan`。
- **空态。** 重新打开搜索并输入 `volcano`。运行 `control-notes browser fill --role searchbox --name "Search notes" --value "volcano"`。搜索完成后出现名为 `No matching notes` 的状态。
- **清除查询。** 选择 `Clear search`。运行 `control-notes browser click --role button --name "Clear search"`。搜索框为空，`Recent notes` 区域取代结果列表。
- **CLI 命中。** 从终端搜索。运行 `control-notes cli -- notes search "quarterly" --format json`。退出码为 `0`，且 stdout 包含一个对象，其标题为 `Quarterly plan`。
- **CLI 未命中。** 搜索一个不存在的值。运行 `control-notes cli -- notes search "volcano" --format json`。退出码为 `0`，且 stdout 为 `[]`。
- **证明。** 捕获有结果的填充状态。运行 `control-notes browser snapshot --aria --path artifacts/search/results.aria.txt` 和 `control-notes browser screenshot --path artifacts/search/results.png`。两件产物都标明了 Notes、查询内容和 `Quarterly plan`。

## Gotchas

- 当编辑器或搜索框获得焦点时按 `/` 会插入文本，而不是打开搜索。
- 结果在短暂的防抖之后更新。要等待结果列表或空态出现，而不是固定休眠。
- 除非用户启用 `Include archived`，否则归档笔记会被排除。
- CLI 默认输出人类可读格式。要得到稳定的断言，请使用 `--format json`。
- 打开某条结果会改变浏览器状态。在证明另一个查询之前，要重新打开搜索。
