# 📊 Financial Sheet Auditor MCP

> Turn Claude, Cursor, and other AI agents into your automated Fractional CFO. Audit financial spreadsheets, catch expense leaks, and project cashflow runway directly from your local machine — without uploading sensitive client data to third-party clouds.

[![MCP Protocol](https://img.shields.io/badge/MCP-Compatible-blue.svg)](https://modelcontextprotocol.io/)
[![Early Access](https://img.shields.io/badge/Status-Public%20Beta-emerald.svg)](#early-access--beta)

---

## 🛑 The Problem
Freelance accountants, fractional CFOs, and solo founders spend hours manually reviewing client export files (QuickBooks, Xero, Stripe, Excel, CSV). 
Standard LLM interfaces fail when handling large financial tables due to context window limits, token costs, and privacy concerns regarding confidential financial figures.

## 💡 The Solution
**Financial Sheet Auditor MCP** exposes lightweight, privacy-first financial inspection tools directly to your AI client via the **Model Context Protocol (MCP)**. Your financial records never leave your local environment.

---

## ⚡ Core Features

* **🔍 Duplicate & Leak Detection:** Identifies recurring double-charges, anomalous vendor billing, and unassigned transaction rows.
* **📈 Anomaly Alert Engine:** Flags any operational or overhead expense deviating more than 30% from the trailing 3-month average.
* **🗓️ 12-Week Cashflow Runway:** Automatically models dynamic burn rate and calculates true runway based on open receivables and scheduled payables.
* **🔒 100% Local & Privacy-First:** Processes CSV and Excel (`.xlsx`) files on your computer. Zero raw financial data is sent to external API databases.

---

## 🛠️ Tools Included in this MCP Server

| Tool | Parameters | Description |
| :--- | :--- | :--- |
| `audit_sheet_health` | `file_path`, `currency` | Scans for duplicates, missing categories, and syntax anomalies. |
| `detect_expense_spikes` | `file_path`, `threshold_pct` | Highlights abnormal vendor costs and line-item variances. |
| `generate_cashflow_runway`| `receivables_path`, `payables_path` | Returns a weekly liquidity forecast and burn projection. |

---

## 🚀 Quick Setup (Claude Desktop)

Add this configuration snippet to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "financial-auditor": {
      "command": "npx",
      "args": ["-y", "financial-sheet-auditor-mcp"]
    }
  }
}
