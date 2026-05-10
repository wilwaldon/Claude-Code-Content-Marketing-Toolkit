# Claude Code Content & Marketing Toolkit

Skills, MCP servers, and tools for content creation, SEO, copywriting, social media, and growth marketing with Claude Code.

`February 2026`

---

## Table of Contents

- [Marketing Skills](#marketing-skills) — CRO, copy, email, ads, growth (Corey Haines)
- [SEO & Discovery](#seo--discovery) — Audits, schema, programmatic SEO, GEO
- [SEO Data (MCP Servers)](#seo-data-mcp-servers) — Live data from Ahrefs, Semrush, GSC, DataForSEO
- [Paid Ads (MCP Servers)](#paid-ads-mcp-servers) — Manage Google Ads campaigns from Claude
- [Content Creation & Repurposing](#content-creation--repurposing) — Write once, publish everywhere
- [Writing Quality](#writing-quality) — Kill the AI slop
- [Research & Trends](#research--trends) — Real-time Reddit/X research
- [Recommended Stacks](#recommended-stacks)
- [Quick Reference](#quick-reference)
- [Further Reading](#further-reading)

---

## Marketing Skills

*Install once, get 23 skills covering the whole marketing stack.*

### Marketing Skills (Corey Haines) — 4.8k stars

23 skills built by the founder of Conversion Factory and Swipe Files. The most adopted marketing skill pack for Claude Code. Covers CRO, copywriting, SEO, email, social, paid ads, analytics, and growth. Each skill auto-activates when Claude detects a relevant task.

| | |
|---|---|
| **Author** | coreyhaines31 |
| **Install** | `npx skills add coreyhaines31/marketingskills` |
| **Source** | [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) |

What's in it:

**Conversion Optimization** — `page-cro`, `signup-flow-cro`, `onboarding-cro`, `form-cro`, `popup-cro`, `paywall-upgrade-cro`

**Content & Copy** — `copywriting`, `copy-editing`, `email-sequence`, `social-content`

**SEO & Discovery** — `seo-audit`, `programmatic-seo`, `competitor-alternatives`, `content-strategy`, `schema-markup`

**Paid & Measurement** — `paid-ads`, `ad-creative`, `ab-testing`, `analytics-tracking`

**Growth & Retention** — `referral-program`, `free-tool`, `churn-prevention`

**Strategy** — `marketing-ideas`, `marketing-psychology`, `pricing-strategy`, `launch-strategy`, `product-marketing-context`, `cold-email`, `revops`, `sales-enablement`

All skills read from a shared `product-marketing-context` file, so Claude knows your product, audience, and positioning before it writes anything.

---

## SEO & Discovery

### Claude SEO (AgriciDaniel)

The most thorough standalone SEO skill. 12 sub-skills, 6 subagents, and a main SKILL.md that orchestrates them. Covers technical SEO, on-page, content, schema, sitemaps, programmatic SEO, competitor pages, hreflang, and GEO (AI search optimization). Updated to INP (replaced FID March 2024) and September 2025 Quality Rater Guidelines.

| | |
|---|---|
| **Author** | AgriciDaniel |
| **Install** | Clone repo, copy to `~/.claude/skills/seo/` |
| **Source** | [AgriciDaniel/claude-seo](https://github.com/AgriciDaniel/claude-seo) |

Slash commands: `/seo audit`, `/seo page`, `/seo schema`, `/seo sitemap generate`, `/seo geo`. Integrates with MCP servers for live data (Ahrefs, Semrush, GSC, DataForSEO). Works without them too — just analyzes what it can see.

The GEO module is the standout. Optimizes content for AI search engines (Perplexity, ChatGPT, Claude) — citation-friendly formatting, entity markup, structured answers. Most SEO tools don't touch this yet.

---

## SEO Data (MCP Servers)

*Skills give Claude SEO knowledge. MCP servers give Claude live SEO data. These connect Claude Code to your actual analytics and keyword tools.*

### Ahrefs MCP (Official)

Pull keyword data, backlink profiles, and site metrics directly from Claude Code. Official from Ahrefs.

| | |
|---|---|
| **Install** | `npx @ahrefs/mcp` |
| **Requires** | Ahrefs subscription |

### Semrush MCP (Official)

Keyword research, competitor analysis, backlink audits, ad copy retrieval. Official from Semrush. Read-only access to all Trends API and Projects API v3.

| | |
|---|---|
| **Docs** | [developer.semrush.com/api/basics/semrush-mcp](https://developer.semrush.com/api/basics/semrush-mcp/) |
| **Requires** | Semrush subscription + API units |

### Google Search Console MCP

Your site's search data in Claude Code. Impressions, clicks, positions, queries. Check which keywords are getting traction while you're writing content.

| | |
|---|---|
| **Source** | [AminForou/mcp-gsc](https://github.com/AminForou/mcp-gsc) |

### DataForSEO MCP

Keyword volumes, SERP analysis, backlink profiles, competitor data — the raw data that powers tools like Ahrefs and Semrush. Pay-per-API-call pricing, no monthly subscription required.

| | |
|---|---|
| **Install** | `npx dataforseo-mcp-server` (pass credentials in Claude config) |
| **Requires** | DataForSEO account |

---

## Paid Ads (MCP Servers)

*Skills give Claude marketing knowledge. MCP servers give Claude live ad-account data and the ability to act on it. These connect Claude Code to your actual ad accounts.*

### NotFair (Google Ads)

Hosted Google Ads MCP server. Diagnose campaign performance (CPA, ROAS, search-term waste, quality scores, learning-phase status), recommend optimizations (bids, budgets, negative keywords, ad copy, audience refinements), and execute approved changes via the official Google Ads API with a built-in human-approval gate.

| | |
|---|---|
| **Source** | [notfair.co](https://notfair.co) |
| **Requires** | Google Ads account |

Free tier available; paid plans for higher usage.

---

## Content Creation & Repurposing

### ClaudeCode Writer (WomenDefiningAI)

A full writing workspace with slash commands and platform-specific agents. The workflow: capture ideas in `/rawnotes`, extract themes with `/extract-themes`, research with `/research`, write with `/write`, then repurpose with specialized agents for LinkedIn, newsletters, X threads, and podcast Q&A scripts.

| | |
|---|---|
| **Source** | [WomenDefiningAI/claudecode-writer](https://github.com/WomenDefiningAI/claudecode-writer) |

You seed it with 3-5 examples of your best writing. Claude learns your voice, then applies it across every output.

---

## Writing Quality

### Humanizer — 2.9k stars

Removes signs of AI-generated writing. Based on Wikipedia's "Signs of AI writing" guide (maintained by WikiProject AI Cleanup). Detects 24+ patterns: inflated symbolism, promotional language, vague attributions, em dash overuse, rule of three, AI vocabulary ("delve", "pivotal", "landscape"), negative parallelisms. Two-pass approach — diagnose, then rewrite.

| | |
|---|---|
| **Author** | blader |
| **Install** | `mkdir -p ~/.claude/skills/humanizer && cp SKILL.md ~/.claude/skills/humanizer/` |
| **Source** | [blader/humanizer](https://github.com/blader/humanizer) |

Fair warning: it makes text *less obviously AI-generated*, but doesn't make it sound like *you*. It strips patterns, it doesn't add voice. Good for a first pass. For voice matching, you need to seed it with your own writing samples.

---

## Research & Trends

### /last30days Skill — 1.3k stars

Researches any topic across Reddit and X from the last 30 days, then writes copy-paste-ready prompts based on what it finds. Pulls from actual threads and posts — not just headlines. Requires OpenAI API key (for Reddit data access) and xAI API key (for X timeline search).

| | |
|---|---|
| **Author** | mvanhorn |
| **Install** | See repo README for setup |
| **Source** | [mvanhorn/last30days-skill](https://github.com/mvanhorn/last30days-skill) |

Example: `/last30days what are the best cold email frameworks right now` — scans Reddit + X, finds what's actually working (with upvote/like counts as signal), then generates a prompt template you can use immediately.

Good for: finding what's trending before you write about it, discovering current frameworks and terminology, generating prompts grounded in real community sentiment.

---

## Recommended Stacks

### Solo founder / startup marketer

```bash
# Full marketing skills suite
npx skills add coreyhaines31/marketingskills

# AI slop removal
mkdir -p ~/.claude/skills/humanizer
# (copy SKILL.md from blader/humanizer)

# Trend research
# (install last30days per repo instructions)
```

Tell Claude about your product first: fill in `product-marketing-context` with your positioning, audience, and value prop. Everything else reads from that.

### SEO-focused content operation

```bash
# SEO skills
git clone https://github.com/AgriciDaniel/claude-seo.git
cp -r claude-seo/* ~/.claude/skills/

# Live keyword data (pick one or combine)
# Ahrefs:
npx @ahrefs/mcp
# DataForSEO (cheaper, pay-per-call):
npx dataforseo-mcp-server

# GSC for your own site data
# (see AminForou/mcp-gsc for setup)

# Content writing + repurposing
npx skills add coreyhaines31/marketingskills --skill copywriting copy-editing content-strategy seo-audit
```

### Content repurposing machine

```bash
# Writing workspace
git clone https://github.com/WomenDefiningAI/claudecode-writer.git
cd claudecode-writer && claude

# Add your writing examples to the workspace
# Use /write -> LinkedIn agent -> Newsletter agent -> Social agent
```

---

## Quick Reference

| Tool | Type | What it does | Setup |
|------|------|-------------|-------|
| Marketing Skills (Corey Haines) | Skills | 23 CRO/copy/SEO/email/growth skills | One command |
| Claude SEO | Skill | 12 sub-skills, 6 subagents, GEO module | Clone repo |
| Ahrefs MCP | MCP | Keyword + backlink data | npx (needs sub) |
| Semrush MCP | MCP | Keyword + competitor + ad data | Config (needs sub) |
| Google Search Console MCP | MCP | Your site's search data | Config + service acct |
| DataForSEO MCP | MCP | Raw SEO data, pay-per-call | npx + credentials |
| ClaudeCode Writer | Workspace | Write once, publish everywhere | Clone repo |
| Humanizer | Skill | Strip AI writing patterns | Manual copy |
| /last30days | Skill | Reddit + X trend research | API keys needed |

---

## Further Reading

| Resource | |
|----------|---|
| [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) | Full skill list with descriptions |
| [AgriciDaniel/claude-seo](https://github.com/AgriciDaniel/claude-seo) | SEO skill docs + MCP integration guide |
| [blader/humanizer](https://github.com/blader/humanizer) | AI writing pattern detection |
| [mvanhorn/last30days-skill](https://github.com/mvanhorn/last30days-skill) | Real-time trend research |
| [WomenDefiningAI/claudecode-writer](https://github.com/WomenDefiningAI/claudecode-writer) | Writing workspace with platform agents |
| [awesome-claude-code](https://github.com/jqueryscript/awesome-claude-code) | Master list of all Claude Code tools |

---

## Contributing

Know a content or marketing tool that should be on this list? Open a PR.

To get included:
- Has to work with Claude Code
- Has to be specifically useful for content, marketing, or SEO work
- Has to be maintained or from a trusted source

---

## License

[MIT](LICENSE)

---

*[wilwaldon.com](https://wilwaldon.com) · February 2026*
