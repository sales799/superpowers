# HCI Talks — CXO Intelligence Platform

## Status: PRE-LAUNCH

## Overview
Platform for C-suite executives offering organizational intelligence, competitor analysis, and hiring insights. Sub-products: CompeteIQ, HireIQ, CVPRO, Talpro integration.

## Live URLs
- **Main:** hcitalks.com
- **Intel:** intel.hcitalks.com (HCI Intel sub-product)

## Tech Stack
- **Framework:** Next.js
- **Port:** 3001 (PM2 managed, cluster mode x2)
- **Path:** /opt/hcitalks
- **Payment:** Razorpay webhook integration (in progress)
- **Auth:** Google OAuth (in progress), MSG91 SMS OTP (DLT registration required)

## Sub-Products
| Product | Purpose |
|---------|---------|
| CompeteIQ | Competitor intelligence |
| HireIQ | Hiring analytics |
| CVPRO | CV evaluation (live Custom GPT, 26,429-line codebase) |
| MEDHA AI | CMO agent (Aarya persona, N8N pipeline: Gemini → Claude → GPT-4o) |

## Key Blockers
- Zero Google indexing (critical SEO blocker)
- MSG91 DLT registration pending
- Progressive commitment UX for CXO registration needs implementation

## Launch Tracking
- Asana project: "Terminator - Final Launch" (30 tasks)

## Security
- Strongest security posture on VPS (6/7 headers, full CSP)
