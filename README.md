# AI to Agent Web Intelligence MCP

把外部網頁資料整理成可追溯、可比較、可交接的企業情報。

**版本 0.1.2｜2026-09-27｜整合指南與工作流教材｜授權 CC BY-SA 4.0**

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](LICENSE) ![版本](https://img.shields.io/badge/version-0.1.2-blue)

![從網頁感知到企業情報：AI to Agent x Scrapling MCP](assets/01-overview.png)

## 統一命名

- Repository：`ai-to-agent-web-intelligence-mcp`
- 專案：AI to Agent Web Intelligence MCP
- 底層：Scrapling 官方 MCP
- 核心：企業情報工作流與 Knowledge Pipeline
- 圖卡：AI to Agent × Scrapling MCP，為底層工具整合的視覺介紹標題。

名稱中的 MCP 表達整合方向，不代表已交付自訂 MCP Server。此版為文件、設定與示範資料。

## 為什麼建立這個專案

企業收集網站資料之後，仍需要整理來源、統一欄位、處理缺漏，再形成可用的決策依據。本專案以 Scrapling 作為網頁擷取引擎，透過 MCP 供 Agent 調用，並補上企業情報工作流的設計與驗收方法。

## 本版交付什麼

- 首頁總覽圖卡及完整文字版，採「幻曜智境・3D 魔幻科技風」。
- 官方 MCP 的安裝與本機連接說明、Claude Desktop 設定範例。
- 企業研究流程、證據欄位、供應商比較示範、人工驗收步驟。
- 原始 Markdown、修訂紀錄、來源、署名、版權及發布檢查。

本版沒有自訂 MCP Server 原始碼，也沒有已部署的監控服務。研究、比較、排程與知識庫寫入屬於工作流規格，不能視為已實作的官方工具。原稿只含安裝前置段落，已原樣留存於 sources/；該目錄為歷史資料，不作安裝依據。

## Web Intelligence Brain 定位

> Scrapling 是 Agent 的眼睛；MCP 是神經接口；企業價值在 Web Intelligence Brain。

這是理解分工的比喻。實際系統由 Agent 統籌工具，並透過 Knowledge Pipeline 完成證據整理及知識交付。

三項核心修正：安裝描述使用 Scrapling browser dependencies；安裝統一為 `scrapling[ai]`；重用官方 MCP，將差異化放在上層企業情報工作流。

詳見 [Web Intelligence 架構](docs/web-intelligence.md)。

官方 Agent Skill 提供開發參考，不會自動完成企業情報流程，也不保證產出的程式碼無誤。

## 三個角色

| 角色 | 工作 | 不代表什麼 |
|---|---|---|
| Scrapling | 擷取網頁與處理動態內容 | 不保證內容正確或每次成功 |
| MCP | 讓 Agent 與工具交換請求及結果 | 不自動提供企業分析或排程 |
| Agent 工作流 | 整理證據、比較、交付 | 不取代重要決策的人員審核 |

## 快速開始

1. 閱讀 [安裝與連接指南](docs/installation.md)。
2. 依 [工作流](docs/workflow.md) 給定目的、允許來源及輸出欄位。
3. 使用 [任務範例](examples/research-task.md)，只替換成有權存取的實際網址。
4. 參考 [示範結果](examples/comparison-demo.md)，保留來源與缺漏。
5. 按 [驗收步驟](docs/acceptance.md) 驗證第一個任務，再擴大使用。

## 輸入、輸出與驗收

輸入：任務目的、來源網址、欄位、截止時間及操作限制。
輸出：Markdown 報告與 JSON 證據紀錄。每個結論必須能回查來源；未知值保留未知，不推填價格或規格。
驗收：來源可追溯、欄位一致、差異有依據、未取得資料有明確狀態。

## 適用場景

原料與競品監測、研究文獻彙整、市場與政策追蹤、知識庫整理。持續監控另需排程器與差異儲存；健康資料整理不等於個人醫療建議。需登入、付費或限制存取的內容應先取得授權；不得以工具能力推定存取權。

## 檔案導覽

| 路徑 | 內容 |
|---|---|
| [docs/installation.md](docs/installation.md) | 安裝與客戶端連接 |
| [docs/workflow.md](docs/workflow.md) | 企業情報流程與責任界線 |
| [docs/card-content.md](docs/card-content.md) | 圖卡文字與風格規格 |
| [docs/acceptance.md](docs/acceptance.md) | 實際環境驗收方法 |
| [docs/sources-and-corrections.md](docs/sources-and-corrections.md) | 來源與原稿修正 |
| [docs/publishing.md](docs/publishing.md) | GitHub 上傳及 Release 說明 |
| [configs/claude-desktop.example.json](configs/claude-desktop.example.json) | 設定範例 |
| [examples/evidence-demo.json](examples/evidence-demo.json) | 模擬證據資料 |
| [sources/original-draft.md](sources/original-draft.md) | 未修改原稿 |
| [VALIDATION.md](VALIDATION.md) | 本次實際檢查結果 |
| [COPYRIGHT.md](COPYRIGHT.md) | 作者、素材與權利範圍 |
| [LICENSE](LICENSE) | CC BY-SA 4.0 授權全文 |
| [VERSION](VERSION) | 版本號單一來源 |

[社群平台完整介紹與三個模擬案例](docs/social-post.md)｜[命名規範](docs/naming.md)

## 版本與未來計畫

版本來源為 VERSION（project.json 同步）。0.1.2 是文件初版，不是自訂伺服器穩定版。本次未進行三個客戶端的連線測試。後續可加入版本鎖定、排程、差異追蹤及知識庫寫入，但須分別實作及驗收。

## 授權與作者

本 repo 文件與範例採 CC BY-SA 4.0，見 [LICENSE](LICENSE)。圖卡素材、Scrapling 及第三方品牌不在此授權範圍內，詳見 [COPYRIGHT.md](COPYRIGHT.md) 與 [第三方聲明](THIRD_PARTY_NOTICES.md)。本專案不是 Scrapling、Anthropic 或 OpenAI 的官方產品。

---
AI Coach 益力康陳董 x CGM Coach 血糖教練 | 2026 AI to Agent
