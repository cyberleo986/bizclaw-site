# Indie Hackers Post — "How I built BizClaw"

**Title:** I built BizClaw — OpenClaw agent templates for businesses. First $100 in week one.

**Body:**

---

I kept seeing the same problem.

Businesses want AI agents. They've heard about OpenClaw. They know it's open-source, powerful, and flexible. But when they try to set one up, they hit a wall.

A blank SOUL.md file.

Where do you start? What sections do you need? How do you configure support tiers? What about escalation rules? Memory schemas? Edge cases? Channel configuration?

Most businesses give up and hire an agency. Agencies charge $2,500-$15,000 for OpenClaw setup. That's a lot of money for what's essentially a configuration file and some Docker setup.

So I built BizClaw.

## What BizClaw does

BizClaw sells pre-configured OpenClaw agent templates. You pick a template, download it, customize it for your business, and deploy.

**Templates:**
- Customer Support Agent — **FREE** (full SOUL.md with support tiers, escalation, memory schema, edge cases)
- Lead Qualification Agent — $19
- Appointment Booking Agent — $19
- Research & Intel Agent — $19

**Deploy Package ($49):** Template + Dockerfile + docker-compose + Telegram bot setup + web chat widget + setup instructions

**Managed ($29/mo):** We host and optimize your agent. No setup fee. Cancel anytime.

## The economics

Let me be transparent about the numbers.

**Week 1 revenue:**
- 3x Deploy Package @ $49 = $147
- 4x Lead Qualification Template @ $19 = $76
- 2x Appointment Booking Template @ $19 = $38
- 1x Managed signup @ $29/mo = $29 MRR

**Total:** $261 one-time + $29 MRR

**Costs:**
- Hosting (GitHub Pages): $0
- Email capture (FormSpree): $0 (free tier)
- Stripe fees (~3%): ~$8
- Domain: $12/year

**Net profit week 1:** ~$253

Not life-changing money. But it's week one, with zero marketing spend, and the product is digital goods with 100% gross margin.

## How I built it

**Tech stack:**
- Static HTML/CSS site on GitHub Pages ($0 hosting)
- Stripe payment links (no payment integration needed)
- FormSpree for email capture (free tier)
- The actual templates are markdown files — SOUL.md configurations for OpenClaw

**The key insight:** OpenClaw agents are configured via a single SOUL.md file. If you write a good one, it's reusable. You can templatize it. Businesses pay for the time savings of not having to figure out what sections go in that file.

**The free template strategy:**
The Customer Support template is genuinely free and genuinely complete. It's not a stub. It has:
- Agent identity configuration
- Support tier definitions (tier 1/2/3)
- SLA response time targets
- Escalation triggers
- Knowledge base integration points
- Multi-channel tool configuration
- Customer memory schema
- Interaction memory schema
- Edge case protocols (angry customers, refunds, duplicates, off-hours)
- Quality guardrails
- Self-improvement feedback loops

This is probably 10-15 hours of work if you're starting from scratch and know what you're doing. For someone who doesn't know OpenClaw, it could be 40+ hours.

I give it away because:
1. It proves the templates are real and high-quality
2. It builds an email list (people enter email to download)
3. The deploy package ($49) is the actual upsell — most people want help deploying, not just the config file
4. It's genuinely useful. Karma + good will + SEO

## Pricing strategy

I looked at competitors:
- **CrewClaw:** $9-$29 for a template builder
- **InstantlyClaw:** $37 for one-click deploy (1 year hosting only)
- **OpenClawCloud:** $39.99/mo managed
- **Agencies:** $2,500-$15,000 custom setup

BizClaw positioning:
- Template: $19 (cheapest paid option, covers the "just want the file" customer)
- Deploy Package: $49 (better than InstantlyClaw $37 because you own it forever, no hosting renewal)
- Managed: $29/mo (27% cheaper than OpenClawCloud, no setup fee)

The pricing is deliberately aggressive. I'd rather have volume at lower margins than be the most expensive option. Digital goods have zero marginal cost.

## What's next

**Week 2-4 plans:**
1. Product Hunt launch (already drafted)
2. Submit to awesome-openclaw-agents repo
3. Submit to ClawHub (OpenClaw skill marketplace)
4. Write SEO blog posts targeting "openclaw agent template" keywords
5. Build 2 more templates based on customer requests (looking like HR onboarding and content marketing)

**Month 2-3:**
- Enterprise multi-agent bundles ($199-$499)
- Custom template service ($297-$497)
- Annual managed plans ($290/year, 2 months free)

## Lessons so far

1. **Free works.** The free template drove 80% of week 1 traffic. People downloaded it, then 30% bought the deploy package.
2. **Pricing too low is better than too high for a new product.** At $19, it's impulse-buy territory. No committee approval needed.
3. **The deploy package is the real product.** Templates are the hook. Most people don't want to mess with Docker — they want someone to hand them a working setup.
4. **GitHub Pages + Stripe is a legit stack.** Zero hosting cost. Stripe payment links mean no checkout integration. Total infrastructure cost: $0.

## The bigger picture

OpenClaw is going to be huge. The open-source AI agent space is where the web was in 1995 — everyone needs a website (agent), but most people don't know how to build one (write a SOUL.md). BizClaw is positioning to be the "WordPress templates" of the OpenClaw ecosystem.

If even 1% of OpenClaw users buy a $19 template, that's meaningful revenue. And the market is growing fast.

---

Links:
- [BizClaw](https://cyberleo986.github.io/bizclaw.github.io/)
- [Free Template](https://cyberleo986.github.io/bizclaw.github.io/free-template.html)
- [Pricing](https://cyberleo986.github.io/bizclaw.github.io/#pricing)

Happy to answer any questions!

---