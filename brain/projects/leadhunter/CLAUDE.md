# LeadHunter v3.0 — Enterprise Signal Intelligence Layer

## Status: ACTIVE BUILD (Revenue-Critical)

## Overview
B2B IT staffing lead detection system. Monitors hiring signals, scores leads using TALPRO-IQ rubric, enriches contacts, and pushes qualified leads into HubSpot CRM pipeline. Runs as N8N workflows on VPS.

## Architecture
- **Engine:** N8N workflows (queue mode, PostgreSQL + Redis)
- **AI:** Claude Opus as primary scoring engine
- **CRM:** HubSpot (deal staging, pipeline automation)
- **Email Discovery:** Snov.io (primary), RocketReach (fallback)
- **Search:** Serper.dev (Google search API)
- **Path:** N8N at port 5678

## Core IP
- **TALPRO-IQ:** Proprietary lead scoring rubric
- **14-field lead card schema**
- **HTML email digest templates**
- **Industry/city targeting lists**

## Pipeline
```
Signal Detection (Serper/Google News/LinkedIn)
  → Claude AI Scoring (TALPRO-IQ)
  → Contact Enrichment (Snov.io → RocketReach)
  → HubSpot Deal Creation
  → Email Digest (6-hour cycles)
```

## SaaS Pricing (for Indian staffing agencies)
| Tier | Price |
|------|-------|
| Starter | ₹2,999/month |
| Growth | ₹5,999/month |
| Enterprise | ₹9,999/month |

## Known Issues
- 403 rate-limit issue on N8N workflows
- 522/503 origin error on hcitalks.com affecting some integrations

## Related
- GCC Expansion Tracker: 41-node N8N workflow (17 source categories)
- LinkedIn enrichment via CVPRO's linkedinService.ts
