# Fincept Terminal（GitHub）

- URL: https://github.com/Fincept-Corporation/FinceptTerminal
- 关键词: financial intelligence platform / terminal / analytics / data connectors / trading / AI agents

---

## 摘要
Fincept Terminal v4 是一个开源的金融智能桌面终端，宣称提供“Bloomberg terminal 级”的性能与分析能力。技术栈为原生 C++20 + Qt6 UI，内嵌 Python 用于金融分析，并支持大量数据源连接器与“AI Agents/投资者人格”等功能。

## 原文摘录（README 关键信息）

### About
> **Fincept Terminal v4** is a pure native C++20 desktop application — a complete rewrite from the previous Tauri/React/Rust stack. It uses **Qt6** for UI and rendering, embedded **Python** for analytics, and delivers Bloomberg-terminal-class performance in a single native binary.

### Features
- **CFA-Level Analytics**：DCF、组合优化、风险指标（VaR、Sharpe）、衍生品定价（通过内嵌 Python）
- **AI Agents**：20+ 投资者人格与策略，本地 LLM 支持，多 provider（OpenAI/Anthropic/Gemini/Groq/DeepSeek/MiniMax/OpenRouter/Ollama 等）
- **100+ Data Connectors**：DBnomics、Polygon、Kraken、Yahoo Finance、FRED、IMF、World Bank、AkShare、政府 API 等
- **Real-Time Trading**：Crypto（Kraken/HyperLiquid WebSocket）、股票、算法交易、paper trading
- **QuantLib Suite**：18 个量化分析模块（定价/风险/随机/波动率/固收等）
- **Visual Workflows**：节点编辑器用于自动化 pipeline、MCP 工具集成
- **AI Quant Lab**：ML、因子发现、HFT、RL trading

### Installation（摘录）
> Clone and run the setup script — it installs all dependencies and builds the app automatically:

```bash
# Linux / macOS
git clone https://github.com/Fincept-Corporation/FinceptTerminal.git
cd FinceptTerminal
chmod +x setup.sh && ./setup.sh
```

### License（摘录）
> **Dual Licensed: AGPL-3.0 (Open Source) + Commercial**

---

## 备注
这份内容基于仓库首页 README 抓取整理（web_crawl）。如果你希望“整篇文章/更完整内容”（包括 docs、wiki、release note），我可以再补抓指定页面/文件并追加到同目录。