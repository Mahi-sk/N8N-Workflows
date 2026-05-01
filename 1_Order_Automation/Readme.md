# 🛒 E-commerce Order Automation — n8n

An automated order processing workflow built with n8n that handles 
the full lifecycle of a new order in real time.

## What It Does
- Receives new orders via webhook (REST API)
- Saves order data to Google Sheets (database)
- Sends confirmation email to customer automatically
- Notifies admin about every new order

## Tech Stack
- **n8n** — workflow automation
- **Google Sheets API** — order database
- **Gmail API** — email notifications
- **Webhook** — REST API trigger

## Architecture
