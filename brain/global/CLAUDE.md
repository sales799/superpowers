# Universal Skills System — 149 Skills across 9 Domains

## How It Works

Skills are markdown files in `~/.claude/skills/` that provide expert-level guidance. They activate automatically based on task context — no manual loading needed. When working on a task, match the domain to the right skill pack.

## Domain Packs

| Pack | File | Skills | Activate When |
|------|------|:------:|---------------|
| Engineering Core | `engineering-core.md` | 23 | Code review, architecture, DevOps, security, testing, data engineering, ML, frontend/backend |
| Engineering Advanced | `engineering-advanced.md` | 25 | CI/CD, database design, API design, migrations, observability, RAG, MCP servers, tech debt |
| Marketing | `marketing.md` | 42 | Content, SEO, CRO, channels (email/social/PPC), growth hacking, market intelligence |
| Product | `product.md` | 8 | Product strategy, UX research, UI design systems, landing pages, SaaS scaffolding |
| C-Level Advisor | `c-level.md` | 28 | CEO/CFO/CMO/COO/CPO/CRO/CTO/CHRO/CISO strategy, board prep, M&A, org health |
| Regulatory & Quality | `regulatory-quality.md` | 12 | FDA, EU MDR, ISO 13485, ISO 27001, GDPR, CAPA, risk management (ISO 14971) |
| Project Management | `project-management.md` | 6 | Jira, Confluence, Scrum, portfolio management, Atlassian admin |
| Business Growth | `business-growth.md` | 4 | Contracts, customer success, revenue ops, sales engineering |
| Finance | `finance.md` | 1 | DCF valuation, financial ratios, budget variance, rolling forecasts |

## Routing Rules

Match tasks to skill packs by context:

- **Writing or reviewing code** → `engineering-core.md`
- **CI/CD, infra, database schema, API contracts** → `engineering-advanced.md`
- **Marketing content, SEO, ads, email campaigns** → `marketing.md`
- **Product decisions, UX, design systems** → `product.md`
- **Executive strategy, fundraising, board prep** → `c-level.md`
- **Compliance, audits, medical devices, GDPR** → `regulatory-quality.md`
- **Jira, Confluence, sprints, project planning** → `project-management.md`
- **Contracts, proposals, revenue operations** → `business-growth.md`
- **Financial modeling, valuations, budgets** → `finance.md`

## Proactive Activation

Some skills auto-trigger on signals:

| Signal | Skill |
|--------|-------|
| Runway < 12 months | CFO Advisor |
| Deployment frequency declining | CTO Advisor |
| NRR below 100% | CRO Advisor |
| Rising CAC trend | CMO Advisor |
| Retention curves not flattening | CPO Advisor |
| Overdue security audits | CISO Advisor |
| Same blocker recurring 3+ weeks | COO Advisor |
| Infinite loop / agent divergence | Agent Protocol |

## Context Budget Guard (CRITICAL)

**"Prompt is too long" prevention — enforce universally:**

1. **Never read skill files > 10KB into main context** — use `Task` subagents instead
2. **Do NOT split large skill files** — route them to Task subagents (they get their own 200K context)
3. **Load skills on-demand** — only when the task needs that specific skill, not preemptively
4. **For advisor-class skills** (CTO, CMO, C-level): always delegate to a Task subagent
5. **MCP budget**: keep < 80 total tools active. Each tool costs ~500-1000 tokens.
6. **If error occurs**: start fresh session, commit work first, don't load skills inline
7. **Multi-file integration work** → use a SINGLE worktree Task subagent (never read 3+ external files into main context)
8. **Parallel agent results** → agents must return summaries (<500 words), write large outputs to files

## Usage

To load a skill pack, read the file from `~/.claude/skills/`. Each pack contains:
- **Activation Index** — table of all skills with trigger keywords
- **Skill Details** — description, sections, output artifacts per skill
- **Proactive Triggers** — conditions for auto-activation (where applicable)
