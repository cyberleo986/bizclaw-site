# BizClaw Agent Deploy Package

_Deploy your AI agent in 10 minutes. Docker, OpenClaw, done._

## What's Included

- **Dockerfile** — Container image with OpenClaw pre-installed
- **docker-compose.yml** — One-command deployment with volumes and health checks
- **.env.example** — Environment variable template (copy to `.env`)
- **SOUL.md** — Your agent's personality, rules, and workflows (from your chosen template)

## Prerequisites

1. **Docker** installed ([get Docker](https://docs.docker.com/get-docker/))
2. **Docker Compose** installed (included with Docker Desktop, or [install separately](https://docs.docker.com/compose/install/))
3. **At least one AI API key** — OpenAI or Anthropic
4. **Channel credentials** — at least one of: Telegram bot token, email IMAP/SMTP, Slack bot token, or Twilio account

## 10-Minute Deploy Guide

### Step 1: Get Your Files (1 min)

Download your template package and copy the deploy files into your project:

```bash
mkdir my-agent && cd my-agent
# Copy the deploy-package files (Dockerfile, docker-compose.yml, .env.example) here
# Copy your chosen SOUL.md here (e.g., lead-qualification-agent/SOUL.md)
```

Your project directory should look like:
```
my-agent/
├── Dockerfile
├── docker-compose.yml
├── .env.example
├── SOUL.md
└── (optionally: AGENTS.md, MEMORY.md)
```

### Step 2: Configure Environment Variables (3 min)

Copy the env template and fill in your credentials:

```bash
cp .env.example .env
```

Open `.env` in your editor and fill in:

**Required:**
- `OPENAI_API_KEY` or `ANTHROPIC_API_KEY` — at least one
- `AGENT_MODEL` — choose your model (default: `anthropic/claude-sonnet-4-20250514`)

**Channel (at least one):**
- `TELEGRAM_BOT_TOKEN` — from [@BotFather](https://t.me/BotFather)
- `IMAP_USER` / `IMAP_PASSWORD` — for email
- `SLACK_BOT_TOKEN` / `SLACK_SIGNING_SECRET` — for Slack
- `TWILIO_ACCOUNT_SID` / `TWILIO_AUTH_TOKEN` — for SMS/voice

**Recommended:**
- `TZ` — set your timezone (e.g., `America/New_York`) so heartbeats run at the right time
- `AGENT_NAME` — give your agent a name

### Step 3: Customize SOUL.md (2 min)

Open `SOUL.md` and update the business-specific sections:

- **Knowledge Base** — replace example services, pricing, hours with your actual data
- **Channels** — uncomment/configure the channels you're using
- **Business rules** — adjust cancellation policies, escalation thresholds, etc.

### Step 4: Build and Start (3 min)

```bash
docker compose up -d --build
```

This will:
1. Build the Docker image (installs OpenClaw + Node.js)
2. Start the container in detached mode
3. Mount persistent volumes for agent memory
4. Begin listening on port 3000

Check that it's running:
```bash
docker compose logs -f
```

You should see OpenClaw start up and connect to your configured channels.

### Step 5: Test Your Agent (1 min)

**If using Telegram:**
- Find your bot on Telegram (the username you set with BotFather)
- Send it a message — it should respond based on your SOUL.md

**If using email:**
- Send an email to your configured IMAP inbox
- The agent should read and respond within a few minutes

**If using web chat:**
- Open `http://localhost:3000` in your browser
- You should see the chat widget

### Done! 🎉

Your AI agent is now running 24/7. It will:
- Monitor your configured channels for incoming messages
- Run heartbeat tasks on schedule (check SOUL.md for your agent's heartbeat routine)
- Persist all memory and interactions to the Docker volumes

## Common Operations

### View logs
```bash
docker compose logs -f --tail=100
```

### Restart the agent
```bash
docker compose restart
```

### Stop the agent
```bash
docker compose down
```

### Update OpenClaw
```bash
docker compose up -d --build
```
This rebuilds the image with the latest OpenClaw version.

### Back up agent memory
```bash
docker compose exec openclaw-agent tar czf - /app/agent/memory > agent-memory-backup.tar.gz
```

### Change the agent model
Edit `.env`, change `AGENT_MODEL`, then:
```bash
docker compose restart
```

## Troubleshooting

**Agent not responding:**
- Check logs: `docker compose logs --tail=50`
- Verify API keys in `.env` are correct
- Ensure at least one channel is properly configured

**Heartbeat not running:**
- Check `TZ` in `.env` is set correctly for your timezone
- Verify the heartbeat schedule in SOUL.md matches your expectations
- Check container is running: `docker compose ps`

**Memory not persisting:**
- Verify volumes are mounted: `docker volume ls | grep agent`
- Don't use `docker compose down -v` (the `-v` flag deletes volumes)

**Port already in use:**
- Change the port mapping in `docker-compose.yml`: `"3001:3000"`

## Production Notes

- **HTTPS:** Use a reverse proxy (nginx, Caddy) or Cloudflare tunnel for HTTPS
- **Scaling:** One container per agent. For multiple agents, use separate compose files
- **Monitoring:** The health check endpoint is at `http://localhost:3000/health`
- **Resource limits:** Add `mem_limit` and `cpus` in docker-compose.yml if needed
- **Secrets:** For production, use Docker secrets or a secrets manager instead of `.env` files

## Support

- OpenClaw docs: [openclaw.com/docs](https://openclaw.com/docs)
- BizClaw templates: [bizclaw.com](https://cyberleo986.github.io/bizclaw-site/)
- Issues: open an issue on the BizClaw GitHub repo

---

_BizClaw — AI agents for small businesses. Built on OpenClaw._