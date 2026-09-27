# Web Intelligence MCP / Knowledge Pipeline

「Web Intelligence Brain」是本專案的架構比喻，不是 Scrapling 官方產品，也不是已實作的大腦服務。「Web Intelligence MCP」是未來可選的自訂接口；Knowledge Pipeline 可由現有 Agent 編排，不必新增 MCP Server。

## 核心架構

Agent 統籌任務；官方 Scrapling MCP 提供網頁工具；上層 Knowledge Pipeline 負責證據、正規化、比較與交付。不要為了命名而再建立一層只轉呼叫 fetch 的伺服器。

| 層次 | 做法 | 本版狀態 |
|---|---|---|
| 擷取與瀏覽器 | 重用 Scrapling 官方能力 | 安裝指南 |
| 工具接口與 Session | 重用官方 MCP | 設定及驗收說明 |
| 情報整理 | 來源、欄位、去重、證據、比較 | 文件規格與模擬案例 |
| 知識交付 | Markdown / JSON；後續接知識庫 | 文件與資料範例 |
| 自訂企業 MCP | 有可重用業務操作時再實作 | 未實作 |

## 三項必改

1. 移除「scrapling install 安裝 Camoufox」的固定說法。教材使用「Scrapling 瀏覽器依賴」；官方 CHANGELOG 的 v0.3.13（2026-01-01）明載 StealthyFetcher 改用 Patchright；這不表示所有 Fetcher 都以 Patchright 為引擎。安裝說明統稱「Scrapling 瀏覽器依賴」，並依目標版本確認。
2. 使用 `python -m pip install "scrapling[ai]"` 與 `scrapling install`。此為使用官方 MCP 的簡化方式，不表示原稿分開安裝一定無效；自訂 MCP 所需 extras 應依實際程式判定。
3. 重用底層，優先實作證據追溯、同基準比較及知識交付。日後自訂工具應回傳資料與狀態，不以漂亮摘要掩蓋缺漏。

## 官方 Agent Skill 的角色

官方 MCP 是供 Agent 調用的工具；官方 Agent Skill 則幫助 coding agent 理解 Scrapling API。兩者用途不同，可依任務搭配。

官方技能名稱為 `scrapling-official`，文件提供以下安裝範例（本次未執行）：

```bash
npx skills add D4Vinci/Scrapling --skill scrapling-official
```

安裝前確認來源與相依需求。官方技能不是本專案所寫，也沒有被複製進本套件；其內容、版本與授權以官方專案為準。

來源：https://scrapling.readthedocs.io/en/latest/ai/agent-skill.html
核對日期：2026-09-27。

---
AI Coach 益力康陳董 x CGM Coach 血糖教練 | 2026 AI to Agent
