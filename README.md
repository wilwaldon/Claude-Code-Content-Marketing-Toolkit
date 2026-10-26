# Claude Code Content & Marketing Toolkit

Skills, MCP servers, and tools for content creation, SEO, copywriting, social media, and growth marketing with Claude Code.

---

## Getting Started

Before you install anything, write your context file. Every skill in this list performs better when Claude knows your product, audience, and positioning.

1. Create `product-marketing-context.md` in your project root
2. Include: what you sell, who buys it, how you talk about it, what makes it different
3. Install the skills and MCP servers that match your workflow
4. Use [claude-goal-scaffold](https://github.com/wilwaldon/claude-goal-scaffold) to run multi-step marketing tasks autonomously with `/goal`

---

## Table of Contents

- [Autonomous Workflows](#autonomous-workflows)
- [Marketing Skills](#marketing-skills)
- [SEO & Discovery](#seo--discovery)
- [SEO Data (MCP Servers)](#seo-data-mcp-servers)
- [Content Creation & Repurposing](#content-creation--repurposing)
- [Writing Quality](#writing-quality)
- [Research & Trends](#research--trends)
- [Recommended Stacks](#recommended-stacks)
- [Quick Reference](#quick-reference)

---

## Autonomous Workflows

### Claude Goal Scaffold

Three-file template for building complete projects with Claude Code's `/goal` command. Set a completion condition, turn on auto mode, and Claude keeps working across turns until a separate evaluator confirms the goal is met. Includes project context template (CLAUDE.md), spec framework (SPEC.md), and workflow guide with goal templates for six project types.

| | |
|---|---|
| **Author** | wilwaldon |
| **Source** | [wilwaldon/claude-goal-scaffold](https://github.com/wilwaldon/claude-goal-scaffold) |

Use this when you're running any multi-step task from this toolkit: full SEO audits, content repurposing pipelines, email sequence builds, or site-wide CRO passes. Write your conditions, set the goal, walk away.

---

## Marketing Skills

### Marketing Skills (Corey Haines)

23 skills covering the full marketing stack. CRO, copywriting, SEO, email, social, paid ads, analytics, and growth. Each skill auto-activates when Claude detects a relevant task. All skills read from a shared `product-marketing-context` file.

| | |
|---|---|
| **Author** | coreyhaines31 |
| **Install** | `npx skills add coreyhaines31/marketingskills` |
| **Source** | [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) |

**Conversion Optimization** — `page-cro`, `signup-flow-cro`, `onboarding-cro`, `form-cro`, `popup-cro`, `paywall-upgrade-cro`

**Content & Copy** — `copywriting`, `copy-editing`, `email-sequence`, `social-content`

**SEO & Discovery** — `seo-audit`, `programmatic-seo`, `competitor-alternatives`, `content-strategy`, `schema-markup`

**Paid & Measurement** — `paid-ads`, `ad-creative`, `ab-testing`, `analytics-tracking`

**Growth & Retention** — `referral-program`, `free-tool`, `churn-prevention`

**Strategy** — `marketing-ideas`, `marketing-psychology`, `pricing-strategy`, `launch-strategy`, `product-marketing-context`, `cold-email`, `revops`, `sales-enablement`

---

## SEO & Discovery

### Claude SEO (AgriciDaniel)

12 sub-skills, 6 subagents, and a main SKILL.md that orchestrates them. Covers technical SEO, on-page, content, schema, sitemaps, programmatic SEO, competitor pages, hreflang, and GEO (AI search optimization). Updated to INP and September 2025 Quality Rater Guidelines.

| | |
|---|---|
| **Author** | AgriciDaniel |
| **Install** | Clone repo, copy to `~/.claude/skills/seo/` |
| **Source** | [AgriciDaniel/claude-seo](https://github.com/AgriciDaniel/claude-seo) |

Slash commands: `/seo audit`, `/seo page`, `/seo schema`, `/seo sitemap generate`, `/seo geo`. Integrates with MCP servers for live data. Works without them too.

The GEO module optimizes content for AI search engines (Perplexity, ChatGPT, Claude) with citation-friendly formatting, entity markup, and structured answers.

---

## SEO Data (MCP Servers)

Skills give Claude SEO knowledge. MCP servers give Claude live SEO data.

### Ahrefs MCP (Official)

Keyword data, backlink profiles, and site metrics directly in Claude Code.

| | |
|---|---|
| **Install** | `npx @ahrefs/mcp` |
| **Requires** | Ahrefs subscription |

### Semrush MCP (Official)

Keyword research, competitor analysis, backlink audits, ad copy retrieval. Read-only access to Trends API and Projects API v3.

| | |
|---|---|
| **Docs** | [developer.semrush.com/api/basics/semrush-mcp](https://developer.semrush.com/api/basics/semrush-mcp/) |
| **Requires** | Semrush subscription + API units |

### Google Search Console MCP

Your site's search data in Claude Code. Impressions, clicks, positions, queries.

| | |
|---|---|
| **Source** | [AminForou/mcp-gsc](https://github.com/AminForou/mcp-gsc) |

### DataForSEO MCP

Keyword volumes, SERP analysis, backlink profiles, competitor data. Pay-per-API-call pricing, no monthly subscription.

| | |
|---|---|
| **Install** | `npx dataforseo-mcp-server` |
| **Requires** | DataForSEO account |

---

## Content Creation & Repurposing

### ClaudeCode Writer (WomenDefiningAI)

Writing workspace with slash commands and platform-specific agents. Capture ideas in `/rawnotes`, extract themes with `/extract-themes`, research with `/research`, write with `/write`, then repurpose with agents for LinkedIn, newsletters, X threads, and podcast Q&A scripts.

| | |
|---|---|
| **Source** | [WomenDefiningAI/claudecode-writer](https://github.com/WomenDefiningAI/claudecode-writer) |

Seed it with 3-5 examples of your best writing. Claude learns your voice and applies it across every output.

---

## Writing Quality

### Humanizer

Removes signs of AI-generated writing. Based on Wikipedia's "Signs of AI writing" guide. Detects 24+ patterns: inflated symbolism, promotional language, vague attributions, em dash overuse, rule of three, AI vocabulary. Two-pass approach: diagnose, then rewrite.

| | |
|---|---|
| **Author** | blader |
| **Install** | `mkdir -p ~/.claude/skills/humanizer && cp SKILL.md ~/.claude/skills/humanizer/` |
| **Source** | [blader/humanizer](https://github.com/blader/humanizer) |

Strips patterns, doesn't add voice. Good for a first pass. For voice matching, seed it with your own writing samples.

---

## Research & Trends

### /last30days Skill

Researches any topic across Reddit and X from the last 30 days, then generates copy-paste-ready prompts based on what it finds. Pulls from actual threads and posts, not headlines.

| | |
|---|---|
| **Author** | mvanhorn |
| **Source** | [mvanhorn/last30days-skill](https://github.com/mvanhorn/last30days-skill) |
| **Requires** | OpenAI API key (Reddit data) + xAI API key (X search) |

Example: `/last30days what are the best cold email frameworks right now` scans both platforms, finds what's working with engagement counts as signal, and generates a prompt template.

### Firecrawl (Official Plugin)

Web research for content and SEO work, with cited sources. Search the web, developer docs, US government publications, and scientific papers, read supplied web pages as Markdown, and look up structured data from Alexandria providers. The plugin also ships SEO audit, lead discovery, business contact research, brand identity, and website design workflows, and connects through Firecrawl's hosted MCP server.

| | |
|---|---|
| **Author** | firecrawl |
| **Install** | `/plugin marketplace add firecrawl/firecrawl-claude-plugin` then `/plugin install firecrawl@firecrawl` |
| **Source** | [firecrawl/firecrawl-claude-plugin](https://github.com/firecrawl/firecrawl-claude-plugin) |
| **Requires** | Firecrawl account ([firecrawl.dev](https://www.firecrawl.dev/?utm_source=claude-code-content-marketing-toolkit&utm_medium=integration)), connected with `/mcp` |

Example: ask for an SEO audit of a page or a cited multi-source research summary and the skills pick the right tools. Commands include `/firecrawl:search`, `/firecrawl:scrape`, and `/firecrawl:agent`.

---

## Recommended Stacks

### Solo founder / startup marketer

```bash
# Marketing skills
npx skills add coreyhaines31/marketingskills

# AI slop removal
# (copy SKILL.md from blader/humanizer to ~/.claude/skills/humanizer/)

# Trend research
# (install last30days per repo instructions)

# Autonomous workflows
# (clone wilwaldon/claude-goal-scaffold)
```

Fill in `product-marketing-context` first. Everything else reads from it.

### SEO-focused content operation

```bash
# SEO skills
git clone https://github.com/AgriciDaniel/claude-seo.git
cp -r claude-seo/* ~/.claude/skills/

# Live keyword data (pick one or combine)
npx @ahrefs/mcp           # Ahrefs
npx dataforseo-mcp-server  # DataForSEO (cheaper, pay-per-call)

# GSC for your own site data
# (see AminForou/mcp-gsc for setup)

# Selective marketing skills
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
| [Goal Scaffold](https://github.com/wilwaldon/claude-goal-scaffold) | Template | Autonomous multi-step project execution | Clone repo |
| [Marketing Skills](https://github.com/coreyhaines31/marketingskills) | Skills | 23 CRO/copy/SEO/email/growth skills | One command |
| [Claude SEO](https://github.com/AgriciDaniel/claude-seo) | Skill | 12 sub-skills, 6 subagents, GEO module | Clone repo |
| [Ahrefs MCP](https://github.com/ahrefs) | MCP | Keyword + backlink data | npx (needs sub) |
| [Semrush MCP](https://developer.semrush.com/api/basics/semrush-mcp/) | MCP | Keyword + competitor + ad data | Config (needs sub) |
| [GSC MCP](https://github.com/AminForou/mcp-gsc) | MCP | Your site's search data | Config + service acct |
| [DataForSEO MCP](https://github.com/nicksona/dataforseo-mcp-server) | MCP | Raw SEO data, pay-per-call | npx + credentials |
| [ClaudeCode Writer](https://github.com/WomenDefiningAI/claudecode-writer) | Workspace | Write once, publish everywhere | Clone repo |
| [Humanizer](https://github.com/blader/humanizer) | Skill | Strip AI writing patterns | Manual copy |
| [/last30days](https://github.com/mvanhorn/last30days-skill) | Skill | Reddit + X trend research | API keys needed |
| [Firecrawl](https://github.com/firecrawl/firecrawl-claude-plugin) | Plugin | Web research, SEO audits, lead and contact research | Plugin install + account |

---

## Contributing

Open a PR. To get included:

- Works with Claude Code
- Specifically useful for content, marketing, or SEO
- Maintained or from a trusted source

---

## License

[MIT](LICENSE)

---

*[wilwaldon.com](https://wilwaldon.com)*
