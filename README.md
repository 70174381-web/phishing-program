# 🎣 Internee.pk — Phishing Simulation & Security Awareness Program

[WEBSITE](https://interneephishingprogram-1.vercel.app/)

![Status](https://img.shields.io/badge/status-internal--use--only-red)
![Tool](https://img.shields.io/badge/tool-GoPhish-0D1B2A?logo=go)
![License](https://img.shields.io/badge/license-MIT-blue)
![Auth Required](https://img.shields.io/badge/authorization-required--before--use-orange)

> **⚠️ Authorization required.** This repository contains templates and tooling for **authorized, internal security awareness simulations only**. Nothing here should be run against any inbox without written sign-off from Leadership, IT/Security, HR, and Legal/Compliance. Read [`docs/rules-of-engagement-template.md`](docs/rules-of-engagement-template.md) first.

---

## 📋 Overview

A complete, production-ready phishing simulation framework for Internee.pk — built on [GoPhish](https://getgophish.com/), an open-source phishing simulation toolkit. The goal is to measure employee susceptibility to common phishing attacks, generate a data-driven security awareness report, and improve resilience through targeted follow-up training.

| | |
|---|---|
| **Organization** | Internee.pk |
| **Primary Tool** | GoPhish (open-source, MIT) |
| **Classification** | Internal / Confidential |
| **Last Updated** | June 2026 |

---

## 📁 Repository Structure

```
internee-phishing-awareness/
│
├── README.md                          ← You are here
├── LICENSE
├── .gitignore
│
├── docs/
│   ├── program-overview.html          ← Full program reference (web page)
│   ├── rules-of-engagement-template.md
│   └── CONTRIBUTING.md
│
├── gophish/
│   ├── config.json                    ← GoPhish server config (edit before use)
│   └── README.md                      ← GoPhish setup walkthrough
│
├── templates/
│   ├── email/
│   │   ├── it-password-expiry.html    ← Template 1: IT urgency lure
│   │   ├── hr-benefits-enrollment.html← Template 2: HR deadline lure
│   │   └── package-delivery.html      ← Template 3: Delivery notification lure
│   └── landing-pages/
│       ├── post-click-explainer.html  ← Shown after a recipient clicks
│       └── submitted-data.html        ← Shown after form submission
│
├── campaigns/
│   ├── wave-1-config.json             ← Example campaign configuration
│   └── target-list-sample.csv        ← CSV format reference (no real emails)
│
├── reports/
│   ├── report-template.md             ← Security Awareness Report outline
│   └── sample-report.md              ← Filled-in example with dummy data
│
├── scripts/
│   ├── import_users.py                ← Bulk-import targets via GoPhish API
│   ├── export_results.py              ← Pull campaign results to CSV/Markdown
│   ├── generate_report.py             ← Build the Security Awareness Report
│   └── requirements.txt
│
└── training/
    ├── red-flags-handout.html         ← One-page employee handout
    └── post-campaign-debrief.md       ← Talking points for the all-hands debrief
```

---

## 🚀 Quick Start

### 1. Prerequisites

| Requirement | Notes |
|---|---|
| Written authorization + signed RoE | See [`docs/rules-of-engagement-template.md`](docs/rules-of-engagement-template.md) |
| Dedicated server / VM | Do **not** run GoPhish on production infrastructure |
| GoPhish binary | [github.com/gophish/gophish/releases](https://github.com/gophish/gophish/releases) |
| Python 3.9+ | For the helper scripts |
| SMTP relay | A dedicated test mailbox with SPF/DKIM configured |

### 2. Install GoPhish

```bash
# Download and verify
wget https://github.com/gophish/gophish/releases/download/v0.12.1/gophish-v0.12.1-linux-64bit.zip
sha256sum gophish-v0.12.1-linux-64bit.zip   # compare against GitHub release page

# Unzip and make executable
unzip gophish-v0.12.1-linux-64bit.zip -d /opt/gophish
chmod +x /opt/gophish/gophish

# Copy and edit the config
cp gophish/config.json /opt/gophish/config.json
# Edit /opt/gophish/config.json — set your admin IP, ports, and cert paths
```

### 3. Start GoPhish

```bash
cd /opt/gophish && ./gophish
# Admin dashboard: https://localhost:3333
# Default credentials are printed to stdout on first run — change them immediately
```

### 4. Import your target list

```bash
pip install -r scripts/requirements.txt

# Edit campaigns/target-list-sample.csv with real (authorized) employee data
# Then import via the GoPhish API:
python scripts/import_users.py \
  --api-key YOUR_GOPHISH_API_KEY \
  --host https://localhost:3333 \
  --csv campaigns/target-list-sample.csv \
  --group-name "Wave 1 - All Staff"
```

### 5. Load templates and launch

Upload the email templates from `templates/email/` and landing pages from `templates/landing-pages/` via the GoPhish web UI, then create a campaign using `campaigns/wave-1-config.json` as a reference.

### 6. Export results and generate report

```bash
python scripts/export_results.py \
  --api-key YOUR_GOPHISH_API_KEY \
  --host https://localhost:3333 \
  --campaign-id 1 \
  --output results/wave-1-results.csv

python scripts/generate_report.py \
  --results results/wave-1-results.csv \
  --output reports/wave-1-report.md
```

---

## 📊 Metrics Tracked

| Metric | GoPhish Event | Why It Matters |
|---|---|---|
| Delivery rate | `email_sent` | Confirms SPF/DKIM/filtering is working |
| Open rate | `email_opened` | Baseline curiosity signal |
| Click-through rate | `clicked_link` | Core susceptibility measure |
| Submission rate | `submitted_data` | Depth of compromise risk |
| Reporting rate | Manual / ticket | The metric to drive up |
| Time-to-first-click | Event timestamp delta | Defender response window |

---

## 🔒 Ethical & Legal Guardrails

- **No real malware, macros, or destructive payloads — ever.**
- **No credential storage** — landing pages capture only the fact of a submission, never a real password.
- **No look-alike production domains** — use an internal test subdomain.
- **No individual-level public reporting** — aggregate by department.
- **Governed by Pakistan's PECA 2016** — get Legal sign-off before launch.

See [`docs/rules-of-engagement-template.md`](docs/rules-of-engagement-template.md) and Section 11 of the full program overview.

---

## 📄 License

MIT — see [LICENSE](LICENSE). This tooling is for **authorized internal use only**; the license does not grant permission to run simulations against organizations or individuals without their explicit written consent.
