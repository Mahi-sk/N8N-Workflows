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
- Webhook → Edit Fields → Google Sheets → Gmail (Customer) → Gmail (Admin)
## How to Run
1. Import `workflow.json` into your n8n instance
2. Connect your Google Sheets and Gmail credentials
3. Activate the workflow
4. Send a POST request to the webhook URL:

```json
{
  "customer_name": "Rahul Shah",
  "email": "customer@email.com",
  "product": "Wireless Headphones",
  "amount": "2999"
}
```

## Business Impact
Eliminates manual order processing — what used to take 
10-15 minutes per order now happens automatically in under 2 seconds.
