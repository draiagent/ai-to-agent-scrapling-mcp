# 來源與修訂說明

文件核對日：2026-09-27。上游 main/latest 是可變來源，不是不可變版本鎖定。

- Scrapling MCP 官方指南：https://scrapling.readthedocs.io/en/latest/ai/mcp-server.html
- 套件設定：https://github.com/D4Vinci/Scrapling/blob/main/pyproject.toml
- 專案及授權：https://github.com/D4Vinci/Scrapling

官方變更紀錄：https://github.com/D4Vinci/Scrapling/blob/main/CHANGELOG.md

官方 Agent Skill：https://scrapling.readthedocs.io/en/latest/ai/agent-skill.html

本次已讀取 MCP、套件設定與 Agent Skill 官方頁面。其他客戶端整合尚未實測。

| 原稿／先前敘述 | 本版處理 |
|---|---|
| 安裝 Camoufox | 改為安裝 Scrapling 瀏覽器依賴，補充 v0.3.13 起 StealthyFetcher 改用 Patchright 的依據 |
| 分別安裝多個套件 | 以官方 MCP extra 安裝路線為主 |
| 自動繞過所有反爬 | 不作成功保證；存取權需獨立確認 |
| 已有完整自訂 MCP | 實際僅有安裝原稿，本版交付文件及設定範例 |
| research_topic 等 | 標示為上層規劃，不冒充官方工具 |
| NotebookLM 自動推播 | 標示為另需整合的寫入流程 |
| 國際糖尿病聯盟（ADA） | 國際糖尿病聯盟通常縮寫為 IDF；避免在本教材沿用混淆稱呼 |

原稿位元組原樣保留，包括未閉合的程式碼圍欄；sources/README.md 明確標示歷史用途。正式操作文件的程式碼圍欄均已檢查。

---
AI Coach 益力康陳董 x CGM Coach 血糖教練 | 2026 AI to Agent
