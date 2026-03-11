# HCI Intel — CXO Organizational Intelligence Platform

## Status: PHASE 1 PENDING

## Overview
216-parameter framework across 18 categories for deep organizational intelligence. Completed CLAUDE.md spec, awaiting Phase 1 execution.

## Architecture
- **Parameters:** 216 across 18 categories
- **Stack:** Next.js + Prisma
- **Path:** /opt/apps/hci-intel
- **PM2:** hci-intel (main) + hci-intel-worker

## Phase 1 Deliverables
1. Prisma migration
2. Parameter seeding (216 parameters into DB)
3. Basic API endpoints for parameter CRUD

## Execution
- Deploy via Claude Code
- CLAUDE.md spec is complete and ready

## Known Issues
- intel.hcitalks.com currently TIMEOUT/unreachable
- May need Nginx config + PM2 process verification
