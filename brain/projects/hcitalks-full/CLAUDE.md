# HCITalks — Project Intelligence

## Project Identity

HCITalks is a Next.js 14 (App Router) web application with TypeScript, Prisma ORM, Tailwind CSS, deployed on a Linux VPS with PM2 process management and Nginx reverse proxy.

**AI Layer**: Navshakti Squad — 9 specialized AI agents (AMBA, APARAJITA, TARA, SHAKTI, GAURI, BHAVANI, SIDHI, MAYA, UMA) coordinated by MEDHA v2.0 master system prompt.

**Knowledge Base**: MEDHA-KB — 128 markdown files across 9 directories (brand-identity, competitive-analysis, customer-success, executive-communications, marketing-content, marketing-operations, product-expertise, sales-enablement, templates).

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | Next.js 14 (App Router) |
| Language | TypeScript (strict) |
| ORM | Prisma |
| Database | PostgreSQL |
| Styling | Tailwind CSS |
| Process Mgr | PM2 (cluster mode) |
| Web Server | Nginx (reverse proxy) |
| Email | Local Postfix SMTP |
| Hosting | Linux VPS |

---

## Skills System

This project uses a two-tier adaptive skills system. **Project-level** skills (`.claude/skills/`) cover HCITalks-specific patterns. **Universal skills** (`~/.claude/skills/`) provide 149 expert skills across 9 domains, available in any project.

### Project Skills (`.claude/skills/`)

| Skill | Triggers | Domain |
|-------|----------|--------|
| `fullstack-architect` | Architecture, scaffolding, patterns | Engineering |
| `frontend-engineer` | Components, UI, Tailwind, performance | Engineering |
| `backend-engineer` | API routes, Prisma, database | Engineering |
| `qa-engineer` | Tests, coverage, E2E | Engineering |
| `devops-engineer` | PM2, deployment, VPS, CI/CD | Engineering |
| `security-engineer` | OWASP, auth, secrets, headers | Engineering |
| `seo-specialist` | Meta tags, sitemap, Core Web Vitals | Marketing |
| `content-strategist` | Content planning, MEDHA-KB, pillar pages | Marketing |
| `ceo-advisor` | OKR cascade, fundraising, board prep, M&A, cap table | Advisory |
| `cfo-advisor` | Financial modeling, pricing, valuation, scenario planning | Advisory |
| `cpo-advisor` | Product discovery, RICE scoring, PLG, experimentation | Advisory |
| `cro-advisor` | Sales methodology, pipeline, revenue forecasting, churn | Advisory |
| `coo-advisor` | Operating cadence, process design, automation, capacity | Advisory |
| `chro-advisor` | Hiring, compensation, performance mgmt, engagement | Advisory |
| `ciso-advisor` | Threat modeling, vulnerability mgmt, IR, compliance | Advisory |
| `cto-advisor` | Architecture decisions, tech debt, scaling | Advisory |
| `cmo-advisor` | Growth model, budget, channels, brand | Advisory |
| `cmo-agent-toolkit` | Marketing tools, MCP integrations, agent orchestration | Marketing/Infra |
| `competitive-ads-extractor` | Competitor ads, messaging analysis, ad libraries | Marketing |
| `content-research-writer` | Blog posts, articles, citations, thought leadership | Marketing |
| `lead-research-assistant` | B2B leads, ICP, lead scoring, outreach strategy | Sales |
| `mcp-builder` | MCP servers, API integrations, tool creation | Engineering |
| `skill-creator` | Creating/updating skills for `.claude/skills/` | Meta |

### Universal Skills (`~/.claude/skills/`) — 149 Skills

| Domain Pack | Skills | Covers |
|-------------|:------:|--------|
| `engineering-core` | 23 | Code review, architecture, DevOps, security, testing, data, ML, full-stack |
| `engineering-advanced` | 25 | CI/CD, database design, API design, migrations, observability, RAG, MCP |
| `marketing` | 42 | Content, SEO, CRO, channels, growth hacking, market intelligence |
| `product` | 8 | Product strategy, UX, design systems, SaaS scaffolding |
| `c-level` | 28 | C-suite advisory, board prep, M&A, org health, scenario planning |
| `regulatory-quality` | 12 | FDA, EU MDR, ISO 13485/27001, GDPR, CAPA, risk management |
| `project-management` | 6 | Jira, Confluence, Scrum, Atlassian admin, portfolio management |
| `business-growth` | 4 | Contracts, customer success, revenue ops, sales engineering |
| `finance` | 1 | DCF valuation, financial ratios, budget variance, forecasts |

### Automatic Skill Activation

When working on a task, load the relevant skill files. **Project skills take precedence** for HCITalks-specific patterns; **universal skills** extend coverage to any domain.

- **Editing `app/` or `components/`** → Load `frontend-engineer` + `fullstack-architect`
- **Editing `app/api/`** → Load `backend-engineer` + `security-engineer`
- **Editing `prisma/`** → Load `backend-engineer` + `fullstack-architect`
- **Working on tests** → Load `qa-engineer`
- **Deployment or PM2** → Load `devops-engineer`
- **Content or MEDHA-KB** → Load `content-strategist` + `seo-specialist`
- **Architecture decisions** → Load `cto-advisor`
- **Marketing strategy** → Load `cmo-advisor` + `cmo-agent-toolkit`
- **Marketing tools / MCP / infrastructure** → Load `cmo-agent-toolkit`
- **CEO / strategy / fundraising / board** → Load `ceo-advisor`
- **Finance / pricing / valuation** → Load `cfo-advisor`
- **Product strategy / prioritization / PLG** → Load `cpo-advisor`
- **Sales / revenue / pipeline / churn** → Load `cro-advisor`
- **Operations / process / automation** → Load `coo-advisor`
- **People / hiring / compensation / culture** → Load `chro-advisor`
- **Cybersecurity / compliance / incidents** → Load `ciso-advisor`
- **Data strategy / analytics / BI** → Load `cdo-cgo-advisor`
- **Security concerns** → Load `security-engineer`
- **Competitive research** → Load `competitive-ads-extractor` + `cmo-advisor`
- **Writing content** → Load `content-research-writer` + `seo-specialist`
- **Lead generation or sales** → Load `lead-research-assistant` + `content-strategist`
- **Building MCP servers** → Load `mcp-builder` + `fullstack-architect`
- **Creating new skills** → Load `skill-creator`
- **Beyond project scope** → Check universal skills index at `~/.claude/CLAUDE.md`

### Slash Commands (`.claude/commands/`)

| Command | Description |
|---------|------------|
| `/git:cm` | Stage and commit (no push) |
| `/git:cp` | Stage, commit, and push |
| `/review` | Quality gate — type check, lint, build, security |
| `/deploy` | Generate VPS deployment checklist |
| `/security-scan` | Dependency audit, secret scan, auth review |
| `/changelog` | Generate customer-facing changelog from git history |

---

## Development Rules

### Code Standards
- TypeScript strict mode — no `any` unless absolutely necessary
- Server Components by default — `'use client'` only when needed
- Prisma for all database access — no raw SQL
- Tailwind CSS for styling — no inline styles
- Conventional Commits — `feat:`, `fix:`, `docs:`, `refactor:`, etc.

### File Organization
```
app/
  (public)/          # Public pages
  (dashboard)/       # Authenticated pages
  api/               # API route handlers
components/
  ui/                # Reusable primitives
  features/          # Feature-specific
lib/                 # Shared utilities
prisma/              # Schema + migrations
MEDHA-KB/            # Knowledge base (128 files)
```

### Git Workflow
- Branch from `main` for features
- Commit and push immediately after completing work (never batch)
- Use Conventional Commit format
- Run `/review` before pushing when possible

### Proactive Checks
Always surface these issues without being asked:
1. **Security** — secrets in code, missing auth on API routes, outdated deps
2. **Performance** — N+1 queries, missing image optimization, bundle bloat
3. **SEO** — missing metadata, broken links, no sitemap
4. **Quality** — TypeScript errors, missing error boundaries, no loading states
5. **Debt** — TODO comments, deprecated APIs, duplicated code

---

## Key Files

| File | Purpose |
|------|---------|
| `prisma/schema.prisma` | Data model definitions |
| `app/layout.tsx` | Root layout + global metadata |
| `next.config.js` | Next.js configuration |
| `tailwind.config.ts` | Tailwind theme + plugins |
| `ecosystem.config.js` | PM2 process configuration |
| `MEDHA-KB/medha-v2-system-prompt.md` | MEDHA master prompt |

---

## Communication Standard

When responding, use this format:
- **BOTTOM LINE** — answer or action first
- **WHAT** — what changed
- **WHY** — reasoning (brief)
- **HOW TO VERIFY** — how to confirm it works

Tag confidence: `[verified]`, `[high-confidence]`, `[assumed — verify]`
