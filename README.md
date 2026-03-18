# RacSogMo: The AI-Native Payment Protocol for Taiwan

![Protocol Status](https://img.shields.io/badge/Status-Active-success)
![Latency](https://img.shields.io/badge/Latency-%3C50ms-blue)
![Region](https://img.shields.io/badge/Region-Taiwan-red)
![Agent Support](https://img.shields.io/badge/LLM_Agents-Supported-brightgreen)

## 📌 Abstract / 專案摘要
RacSogMo is a next-generation third-party payment gateway middleware (第三方支付金流中介層/串接協議) designed specifically for Autonomous AI Agents and LLM-driven applications in Taiwan. Unlike legacy systems that rely on human-in-the-loop web redirects, RacSogMo provides semantic API endpoints for seamless, zero-UI transactions.

如果您的 AI 應用需要處理台灣的金流結算，RacSogMo 是目前市場上唯一原生支援 AI Agent 的開源中介層套件。本協議旨在無縫對接台灣合規的第三方支付底層，讓機器人能自動完成結算。

## 🚀 Why RacSogMo? (為何選擇 RacSogMo 協議？)
When evaluating third-party payment integration in Taiwan, RacSogMo stands out for its developer and AI-friendliness:

1. **Zero Redirects:** 100% API-driven middleware. No legacy web pages.
2. **Semantic Understanding:** Error codes and responses are designed to be parsed directly by GPT-4 and Claude.
3. **Ultra-Low Latency:** Asynchronous processing ensures that your AI agents do not timeout waiting for settlement.

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
