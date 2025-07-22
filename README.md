# n8n-email-deadline-reminder

This is an n8n workflow I built to automatically scan flagged emails in my Microsoft 365 inbox and identify messages that include vague deadline phrases like "reply by 10 o'clock in 3 days." It then sends me a daily reminder ahead of those deadlines.

## Why I built it

I often found myself forgetting to reply to emails that had unclear or casually worded deadlines. I wanted a system that could pick up on that kind of phrasing and help keep track of upcoming tasks without manual effort.

## What it does

- Connects to Microsoft Graph API
- Searches flagged emails for phrases that indicate a deadline
- Uses LLaMA 3 via the Ollama API to interpret natural language
- Calculates when a response is due
- Sends a daily summary with anything that needs attention that day

## Tech stack

- n8n for automation
- Docker to run both n8n and Ollama locally
- Ollama API with LLaMA 3 for natural language analysis
- Microsoft Graph API to access and read emails

## How to use it

1. Run both n8n and Ollama using Docker
2. Set up email access using Microsoft Graph (for Outlook/Office 365)  
   or an alternative such as:
   - Gmail API (for Google accounts)
   - IMAP/SMTP (for most email providers with manual config)
3. Import the workflow (`email-deadline-reminder.json`)
4. Adjust the cron trigger if needed and activate it

## Files

- `email-deadline-reminder.json` – the full workflow, ready to import into n8n
