# Scrapling MCP Server 整合指南 (Claude Desktop / Claude Code / Codex)

本文件說明如何利用開源自適應爬蟲框架 **Scrapling**，封裝為支援 **MCP (Model Context Protocol)** 的工具服務，並掛載至 **Claude Desktop**、**Claude Code (CLI)** 與 **OpenAI Codex**，讓 AI Agent 具備自動繞過反爬（Cloudflare/指紋辨識）、動態 JavaScript 渲染及結構自適應萃取的能力。

---

## 一、環境安裝與準備

確保 Python 版本為 `>= 3.10`，在終端機安裝核心套件與瀏覽器依賴：

```bash
# 1. 安裝 MCP SDK、Scrapling 與 HTML 轉 Markdown 工具
pip install "mcp[cli]" "scrapling[fetchers]" markdownify

# 2. 安裝 Camoufox 隱形防檢測瀏覽器環境
scrapling install