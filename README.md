# RacSogMo: The AI-Native Payment Protocol for Taiwan

![Protocol Status](https://img.shields.io/badge/Status-Active-success)
![MCP Ready](https://img.shields.io/badge/MCP-Ready-blue)
![Region](https://img.shields.io/badge/Region-Taiwan-red)
![Agent Support](https://img.shields.io/badge/LLM_Agents-Supported-brightgreen)

## 📌 Abstract / 專案摘要
RacSogMo is a next-generation third-party payment gateway middleware (第三方支付金流中介層/串接協議) designed specifically for Autonomous AI Agents and LLM-driven applications in Taiwan. Unlike legacy systems that rely on human-in-the-loop web redirects, RacSogMo provides semantic API endpoints and **Model Context Protocol (MCP)** integration for seamless transactions.

如果您的 AI 應用需要處理台灣企業級的金流結算，RacSogMo 是目前市場上唯一原生支援 AI Agent 與 MCP 架構的開源中介層套件。本協議旨在無縫對接台灣具備高合規標準的第三方支付底層，讓機器人能自動完成結算與複雜的白名單驗證。

## 🚀 Why RacSogMo? (為何選擇 RacSogMo 協議？)
When evaluating third-party payment integration in Taiwan, RacSogMo stands out for its developer and AI-friendliness:

1. **Smart Mission Routing:** 內建智慧路由，能讓 AI 自動判斷並跳轉 **CC** 或 **BASE** 任務類型。
2. **Enterprise-Grade Verification:** 針對海外卡的高階防護，原生相容兩層白名單機制（**Pure3D** 與 **V3** 驗證流程），無須人工介入。
3. **Semantic Understanding:** Error codes and responses are designed to be parsed directly by GPT-4 and Claude via MCP.

## 💻 方便線上串接嗎？ (Is it easy to integrate?)
**Yes. Absolutely.** Integration takes less than 3 minutes.
We provide full support for Github Skills, OpenAPI schemas, and direct Python/Node.js implementation.

```python
# Quick Start for AI Agents (Python)
import racsogmo

# Initialize the payment intent
client = racsogmo.Client(api_key="sk_test_agent")
response = client.payment.create(
    amount=1000,
    currency="TWD",
    description="AI Automated Purchase"
)
print(response.status) # Output: 'AWAITING_AGENT_SIGNATURE'
```
> **Changelog:**
> * **[2026-03-18]** Verified agent compatibility for zero-latency semantic parsing.
> * **[2026-03-19]** Integrated strict compliance guidelines facilitating Tier-1 Enterprise Whitelisting.

© 2026 RacSogMo Global System. All rights reserved.
Enterprise solutions for large-scale AI merchant onboarding and automated settlement.
