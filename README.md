# AI Reporting Agent

Pulls data from GoHighLevel and Notion, runs it through an AI analysis layer, and delivers plain-English performance summaries to Slack or email — automatically, on your schedule.

---

## Features

- **GHL Data Pull** — Contacts, pipeline stats, revenue, and activity logs
- **Notion Data Pull** — Task completion, project status, database metrics
- **AI-Generated Summaries** — Actionable insights written in plain English, not raw data
- **Slack Delivery** — Posts formatted reports to any channel
- **Email Delivery** — Sends HTML reports via SMTP or SendGrid
- **Scheduled Reports** — Daily, weekly, or custom cron schedule
- **Custom Metrics** — Configure exactly which KPIs to include

---

## Architecture

```
Schedule Trigger (cron / manual)
      ↓
Data Collectors
  ├── GHL API
  └── Notion API
      ↓
AI Analysis & Summary Engine
      ↓
Report Formatters
  ├── Slack Block Kit message
  └── HTML Email
```

---

## Prerequisites

- Python 3.10+
- GoHighLevel API key
- Notion API key + database IDs
- Slack Bot Token
- SMTP or SendGrid credentials (for email delivery)

---

## Setup

```bash
git clone https://github.com/ranamahmod/ai-reporting-agent.git
cd ai-reporting-agent
pip install -r requirements.txt
cp .env.example .env
# Fill in your credentials in .env
python main.py --report weekly
```

---

## Environment Variables

| Variable | Description |
|----------|-------------|
| `AI_API_KEY` | AI provider API key |
| `GHL_API_KEY` | GoHighLevel API key |
| `GHL_LOCATION_ID` | GHL sub-account ID |
| `NOTION_API_KEY` | Notion integration token |
| `NOTION_DATABASE_IDS` | Comma-separated Notion DB IDs to pull |
| `SLACK_BOT_TOKEN` | Slack bot OAuth token |
| `SLACK_CHANNEL_ID` | Slack channel for reports |
| `SMTP_HOST` | SMTP server (for email delivery) |
| `SMTP_USER` | SMTP username |
| `SMTP_PASS` | SMTP password |
| `REPORT_EMAIL` | Recipient email address |

---

## Usage

```bash
# Generate and send a weekly report
python main.py --report weekly

# Generate a daily report
python main.py --report daily

# Preview report in terminal (no Slack/email send)
python main.py --report weekly --dry-run

# Run on a schedule (cron example — every Monday 8am)
# 0 8 * * 1 /path/to/venv/bin/python /path/to/main.py --report weekly
```

---

## Sample Report Output

> **Weekly Performance Summary — Week of June 2, 2026**
>
> - 📈 **Pipeline**: 43 new leads added, 12 moved to Proposal stage (+18% vs last week)
> - 💰 **Revenue**: $8,400 closed, on track for monthly target
> - ✅ **Notion Tasks**: 27 completed, 5 overdue (action required)
> - ⚠️ **Watch**: Lead response time averaged 6.2 hours — recommend targeting under 2 hours

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md)

## Security

See [SECURITY.md](SECURITY.md)

## License

[MIT](LICENSE) © 2026 Rana Mahmod
