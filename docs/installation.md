# 安裝與連接指南

本版採官方 Scrapling MCP，先以本機 stdio 驗收。以下為文件範例，未在本次環境安裝或啟動。

## 建立隔離環境

本次核對上游 main 的 pyproject.toml，專案版本欄為 0.4.15，requires-python 為 >=3.10。這是文件核對基準，並非本機實測或 PyPI 可用性確認；安裝時仍應核對解析出的相依需求。

```bash
python -m venv .venv
```

Windows PowerShell：
```powershell
.venv\Scripts\Activate.ps1
```

macOS / Linux：
```bash
source .venv/bin/activate
```

```bash
python -m pip install "scrapling[ai]"
scrapling install
scrapling-mcp --help
```

安裝成功後記錄實際版本：
```bash
python -m pip show scrapling
python -m pip freeze > requirements.local.txt
```

此檔供自己的環境重現；本套件不把未實測版本包裝成 lockfile。瀏覽器下載與系統依賴需符合實際作業系統。

## Claude Desktop

合併 configs/claude-desktop.example.json 的 mcpServers 項目到客戶端設定，勿覆蓋其他服務。將 command 改成你環境中 scrapling-mcp 的絕對路徑。Windows 可用 `where.exe scrapling-mcp`；macOS/Linux 可用 `command -v scrapling-mcp`。JSON 中 Windows 反斜線需寫成雙反斜線。

重新啟動客戶端，檢查服務狀態與工具列表。

## Claude Code 與 Codex（通用連接原則）

不同客戶端未必有相同的設定介面。依各版本官方文件或 CLI help 註冊本機 stdio server：服務名 scrapling，command 填上述絕對路徑，args 為空陣列。不要把終端機虛擬環境的 PATH 視為桌面客戶端必然可見。

各客戶端設定格式可能不同；本套件不以 Claude Desktop JSON 冒充通用格式。請依安裝版本的 `claude mcp --help` 或 `codex mcp --help` 核對註冊方法，然後完成 docs/acceptance.md 的驗收。

## 執行與故障處理

stdio 由客戶端啟動程序，不能把沒有終端機文字輸出誤判為掛起。找不到命令時核對絕對路徑；瀏覽器缺失時確認使用相同虛擬環境安裝；工具存在但抓不到正文時先檢查頁面是否需 JavaScript、登入或已改版。

遠端 HTTP 應另行依官方文件設定驗證、網路邊界與允許主機。此版本沒有提供公開 HTTP 部署設定。

官方參考：https://scrapling.readthedocs.io/en/latest/ai/mcp-server.html

---
AI Coach 益力康陳董 x CGM Coach 血糖教練 | 2026 AI to Agent
