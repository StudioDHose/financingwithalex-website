# Financing with Alex — Website

Static site for **Financing with Alex** (West Capital Lending, Inc.).
Deployed on Vercel. Each `.html` file is served at its path without the extension
(e.g. `privacy.html` → `/privacy`).

## Pages
| File | URL | Purpose |
|------|-----|---------|
| `index.html` | `/` | Main site + 6-step qualification quiz (pop-up) |
| `fast-track.html` | `/fast-track` | Fast single-screen lead form (A2P registration URL) |
| `heloc.html` | `/heloc` | Long HELOC application (4 sections) |
| `dscr-application.html` | `/dscr-application` | DSCR application (from email button) |
| `privacy.html` | `/privacy` | Privacy Policy |
| `terms.html` | `/terms` | Terms of Use |
| `sms-terms.html` | `/sms-terms` | SMS Terms |

## Before going fully live
- [ ] Paste the GHL inbound webhook URL into `GHL_WEBHOOK_URL` in index, fast-track, heloc, dscr-application
- [ ] Fill the effective `[date]` in privacy / terms / sms-terms
- [ ] West Capital Lending to approve policy & consent text
- [ ] Confirm Supabase RLS: anon = INSERT only on the leads table
- [ ] Build remaining page: `/dscr` (long investor form)

## Compliance notes
- **No SSNs anywhere.** SSN is collected by phone by the loan officer, never on the site.
- Consent checkboxes are unchecked by default and optional (A2P carrier rules).
- Texting brand: West Capital Lending, Inc. (Company NMLS #1566096).

## Stack
Plain HTML/CSS/JS. Supabase (leads capture, anon key is public by design, protected by RLS).
Built by Studio D'Hose.
