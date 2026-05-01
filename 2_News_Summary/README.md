# 📊 AI-Powered Tech News Digest Bot (n8n Automation)

An automated workflow built using **n8n**, **NewsAPI**, and **Claude AI** that fetches the latest technology news, summarizes it using AI, and delivers it directly to Telegram every 6 hours.

---

## 🚀 Features

- 🔄 Fully automated scheduled execution (every 6 hours)
- 📰 Fetches latest tech news using NewsAPI
- 🤖 AI-powered summarization using Claude (Anthropic)
- 💬 Clean, structured news digest formatted for Telegram
- 📲 Instant delivery via Telegram bot
- 🔐 Secure environment-based API key management

---

## 🏗️ Workflow Architecture

1. **Schedule Trigger**
   - Runs the workflow every 6 hours automatically

2. **HTTP Request (NewsAPI)**
   - Fetches top technology headlines

3. **JavaScript Code Node**
   - Formats and structures raw news data

4. **AI Model (Claude)**
   - Summarizes news into concise bullet points

5. **Telegram Node**
   - Sends final digest to user

---

## 🧰 Tech Stack

- n8n (Automation Platform)
- NewsAPI (News data source)
- Anthropic Claude (AI summarization)
- Telegram Bot API
- JavaScript (data processing)

---

## 🔐 Environment Variables

Create a `.env` file locally:

```bash
NEWS_API_KEY=your_newsapi_key_here
