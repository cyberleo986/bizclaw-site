# Indie Hackers Post — How I Built BizClaw

**Title:** How I Built BizClaw — OpenClaw Agent Templates from $19, Undercutting Every Competitor

---

## The Problem

I spent 3 weekends trying to set up my first OpenClaw agent. I read the docs, wrote SOUL.md files, configured channels, set up Docker — and after 20+ hours, I had... a broken Telegram bot that kept crashing.

The docs are great if you're a developer. But most business owners? They just want an AI support rep that works.

## The Research

Before building, I researched every competitor:

| Competitor | Price | What You Get |
|---|---|---|
| CrewClaw | $29 one-time | Builder only, no deploy |
| InstantlyClaw | $37 one-time | 1 year hosting limit |
| OpenClawCloud | $39.99/mo | Managed hosting |
| Simular.ai | $20-$500/mo | Desktop app |
| Agencies | $2,500-$15,000 | Custom setup |

**The gap:** Nobody offers a complete deploy package at a price that doesn't make you wince.

## The Solution

**BizClaw** — production-ready OpenClaw agent templates.

**Pricing (intentionally aggressive):**
- **$19** — Template only (SOUL.md + config files)
- **$49** — Full deploy package (template + Docker + bot integrations + setup guide)
- **$29/mo** — Managed hosting (cheaper than OpenClawCloud)

**How it works:**
1. Pick a template (support, sales, booking, research)
2. Download instantly
3. Customize in 60 seconds
4. Deploy in 10 minutes with Docker

**What's inside each template:**
- Complete SOUL.md with personality, tone, boundaries
- Knowledge base (shipping, returns, common issues)
- Escalation rules (knows when to hand off to humans)
- Multi-channel config (Email, Telegram, Web Chat, WhatsApp)
- Customer memory tracking
- Heartbeat configuration for proactive tasks

## The Stack

- **Site:** GitHub Pages (free hosting)
- **Payments:** Stripe (one-time + subscription)
- **Email capture:** Formspree (free tier)
- **Templates:** Markdown + Docker
- **Deploy:** Docker Compose + self-hosted OpenClaw

**Total cost to build:** $0 (GitHub Pages) + 2 weekends of my time.

## The Launch

**Week 1:**
- Product Hunt launch
- OpenClaw Discord #showcase
- r/OpenClaw post
- Submit to awesome-openclaw-agents GitHub repo
- ClawHub marketplace submission

**Week 2:**
- SEO content ("best OpenClaw templates", "OpenClaw setup guide")
- YouTube tutorial: "Deploy an AI agent in 10 minutes"
- Partner with OpenClawReady ($200-500 setup service → refer to $49 option)

**Month 2:**
- Google Ads targeting "OpenClaw templates"
- Reddit ads in r/smallbusiness
- Trades vertical: cold email to Phoenix roofers/plumbers (site already has trades templates)

## Revenue Model

**Conservative estimates:**
- 10 template sales/month at $19 = $190
- 5 deploy packages/month at $49 = $245
- 3 managed customers at $29/mo = $87
- **Total: ~$522/month** in month 1

**If it scales:**
- 100 template sales = $1,900
- 50 deploy packages = $2,450
- 30 managed = $870
- **Total: ~$5,220/month**

## Free Download

Grab the Customer Support Agent SOUL.md template for free — no email required:
https://cyberleo986.github.io/bizclaw-site/free-template.html

## Lessons

1. **One-time pricing wins.** People hate subscriptions for templates. $49 one-time feels like a steal vs $39.99/mo forever.
2. **Free lead magnets work.** Give away one template, sell the deploy package. 80% of free downloaders never buy, but 20% convert to paid.
3. **Compete on value, not features.** CrewClaw has a visual builder. We have a complete Docker package. Different value prop, same price.
4. **Niche down.** Trades businesses (roofers, plumbers, HVAC) have zero AI setup. Massive underserved market.

## What's Next

- Add 10 more templates (sales, marketing, ops)
- Build a template marketplace (other creators can sell)
- Launch on Product Hunt (next Tuesday)
- YouTube content series

**Site:** https://cyberleo986.github.io/bizclaw-site/

Questions? Ask me anything.
