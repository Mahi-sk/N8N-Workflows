# 🎙 Podcast Summarizer Bot — n8n Workflow

A Telegram bot that takes any YouTube podcast link and returns a brutally concise deep analysis — key questions, highlights, controversial opinions, and a one-line verdict.

---

## What It Does

Send any YouTube podcast URL to your Telegram bot and get back:

- What the conversation is really about
- Key questions discussed with actual answers
- Highlights worth remembering
- Controversial or strong opinions
- One line verdict

---

## Tech Stack

| Service | Purpose |
|---------|---------|
| n8n | Workflow automation |
| Telegram Bot | Input and output interface |
| Supadata API | Fetch YouTube transcript |
| YouTube oEmbed | Fetch video title and channel |
| Anthropic (Claude) | AI analysis and formatting |

---

## Setup Instructions

### 1. Clone or import the workflow
Import `podcast_summarizer_workflow.json` into your n8n instance via:
Settings → Import Workflow

### 2. Set up credentials in n8n

You need to create these credentials inside n8n before the workflow runs:

#### Telegram Bot
- Go to Telegram → search @BotFather
- Send /newbot and follow the steps
- Copy the Bot Token
- In n8n → Settings → Credentials → New → Telegram API → paste token
- Replace all `YOUR_TELEGRAM_CREDENTIAL_NAME` references in the workflow with your credential name

#### Supadata API
- Sign up free at https://supadata.ai
- Go to Dashboard → API Keys → copy your key
- In the HTTP Request node (Supadata) → Headers → replace `YOUR_SUPADATA_API_KEY` with your actual key

#### Anthropic API
- Get your key from https://console.anthropic.com
- In n8n → Settings → Credentials → New → Anthropic API → paste key
- Replace `YOUR_ANTHROPIC_CREDENTIAL_NAME` in the workflow with your credential name

### 3. Activate the workflow
- Toggle the workflow to Active in n8n
- Send any YouTube podcast link to your bot on Telegram

---

## What Was Fixed vs Original

| Issue | Fix |
|-------|-----|
| Supadata API key was hardcoded | Replaced with placeholder |
| Chat ID was hardcoded | Now dynamic from Telegram trigger |
| Transcript reference was broken | Fixed to use correct node reference |
| Parse mode was HTML causing errors | Removed parse mode — plain text only |
| System prompt was missing | Added as separate system message |
| Model was claude-opus-4-7 (wrong) | Updated to claude-sonnet-4-20250514 |

---

## Environment Variables (if self-hosting n8n)

If you are running n8n locally with a .env file, you can set:

```
SUPADATA_API_KEY=your_key_here
TELEGRAM_BOT_TOKEN=your_token_here
ANTHROPIC_API_KEY=your_key_here
```

Then reference them in n8n nodes using `{{ $env.SUPADATA_API_KEY }}`

---

## Notes

- Free Supadata tier gives 100 transcripts/month — enough for personal use
- Works with any YouTube URL format (full, short, with timestamps)
- If a video has no transcript available, the workflow will fail gracefully at the HTTP Request node
