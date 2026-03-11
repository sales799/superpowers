# Jharokha — QR Smart Doorbell PWA

## Status: PRIMARY ACTIVE PROJECT

## Overview
Consumer-grade QR smart doorbell PWA under the Rakshakawach parent brand. Visitors scan a QR code on the door, leave a message/photo/video — resident gets instant notification. No hardware, no wiring, no Wi-Fi needed at the door.

## Live URLs
- **App:** app.jharokha.space
- **Marketing site:** jharokha.space

## Tech Stack
- **Frontend:** Next.js (PWA)
- **Backend:** Node.js API (85+ endpoints)
- **Database:** PostgreSQL (34 tables)
- **Deployment:** Docker container on Hostinger KVM4
- **Process:** PM2 managed
- **Path:** /opt/jharokha

## Pricing
| Plan | Price | Features |
|------|-------|----------|
| Plus | ₹59/month | Single doorbell, notifications |
| Family | ₹99/month | Multi-doorbell, family members |

## Billing
- Razorpay (INR subscriptions)
- GSTIN on invoices: 29AAHCT9485A1ZX (Talpro India Pvt Ltd)

## Key Milestones Completed
- Migrated from Replit → Hostinger VPS
- Docker containerized
- 4 sprints, 83 features catalogued
- Pre-launch security audit completed
- 27 use cases across 7 categories identified

## Known Issues
- app.jharokha.space HTTP 526 error (origin SSL cert issue inside Docker — Cloudflare can't complete handshake)
- Security headers: only 2/7 passing (missing CSP, X-Frame-Options, Referrer-Policy)

## Quality Bar
Consumer-grade product = highest uptime + performance standards across all projects.
