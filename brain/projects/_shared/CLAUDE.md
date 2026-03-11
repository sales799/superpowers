# Talpro Universe — Shared Context

## Owner
- **Name:** Bhaskar Anand
- **Company:** Talpro India Private Limited
- **Role:** Founder (non-technical — Claude is virtual CTO)
- **Location:** Bengaluru (Begur), Karnataka, India
- **GSTIN:** 29AAHCT9485A1ZX (Provisional, Karnataka)
- **PAN:** AAHCT9485A

## VPS — Hostinger KVM4
- **IP:** 147.93.103.194
- **SSH:** Port 2244 (Hostinger blocks 22). Mac alias: `talpro-vps`
- **OS:** Ubuntu 24.04
- **Specs:** 16GB RAM, 8 vCPU, 400GB NVMe (locked until 2027-11-15)
- **Stack:** PM2 + Nginx + Let's Encrypt SSL + UFW (22/80/443)
- **Services:** PostgreSQL, Redis, N8N (queue mode, port 5678), Prometheus, Grafana
- **No GPU** — CPU-only inference

## Directory Map
| Path | Project |
|------|---------|
| /opt/jharokha | Jharokha PWA |
| /opt/hcitalks | HCI Talks platform |
| /opt/apps/hci-intel | HCI Intel |
| /opt/929digital | 929.Digital |
| /opt/talpro-india | Talpro website |
| /opt/talpro-mcp-server | This MCP server |

## AI Accounts
- Claude Max: bhaskar@talpro.in (Org: 54eb4365) + bhaskar@talproindia.com (Org: 4193ab14)
- Both 20x Pro usage, renew Apr 10 2026
- Gemini Ultra via Antigravity
- GitHub: sales799

## Conventions
- **Deploy terminal:** Claude Code Desktop
- **Process manager:** PM2 for all Node.js services
- **Reverse proxy:** Nginx only (no Apache/Caddy)
- **SSL:** Let's Encrypt via Certbot
- **Firewall:** UFW — ports 22, 80, 443 only
- **One change at a time** — never deploy multiple changes simultaneously
- **Cost > Performance > Scalability > Simplicity** (CTO priority order)
- **Jharokha** = consumer-grade standards (highest uptime bar)
- **LeadHunter** = revenue-critical (downtime = lost business)

## Brand Universe
| Brand | What | Status |
|-------|------|--------|
| Talpro India | IT contract staffing (15+ yrs) | Active/Revenue |
| Jharokha (Rakshakawach) | QR smart doorbell PWA | Primary Active |
| HCI Talks | CXO intelligence platform | Pre-launch |
| HCI Intel | 216-parameter org intelligence | Phase 1 pending |
| LeadHunter v3.0 | B2B IT staffing lead detection | Active build |
| 929.Digital / Flexiwork | Virtual office / coworking | In dev |
| TARA-CCO | 12-agent AI compliance officer | Blueprinted |
| CVPRO | CV evaluation (Custom GPT) | Live |
| CompetitorX | AI automation | Pre-launch |
| Catalyzer Labs | Startup incubation | Pre-launch |
| Elovia | FMCG cleaning brand | Pre-launch |
| HourlyTechJobs.com | Gig tech marketplace | Pre-launch |
