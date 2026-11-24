# 大顶子荐股模拟盘

- `picks.csv`：推荐清单（大顶子格式）。新推荐直接往后追加行。
  - BUY = 条件突破单；FILL = 大哥实际买入（价格写在 limit 列）；SOLD = 大哥实际卖出（价格写在 limit 列，迫子扩展）。
- `python3 sim.py`：下载雅虎 5 分钟K线（近 1 个月）重算，生成 `site/index.html` 和 `sim_result.json`。`--offline` 用 `data/` 缓存。
- `template.html`：页面模板。`site/` 整个目录可直接放到 GitHub Pages（仓库根目录放 index.html）。
- 页面打开时会用 CNBC 报价接口（允许跨域）刷新持仓和挂单的现价；成交/止损判断以脚本运行时的快照为准。
- 注意：5 分钟K线只保留约 60 天，range=1mo；推荐早于 1 个月的要改 sim.py 里的 range。
