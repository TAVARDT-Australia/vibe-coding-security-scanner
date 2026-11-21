# Vibe Coding Security Scanner & AI-Generated App Auditor | TAVARDT Australia

[![Licence MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Vibe Coding Security](https://img.shields.io/badge/Vibe%20Coding-Security%20Hardened-00d26a.svg)](README.md)
[![Language](https://img.shields.io/badge/Language-English%20(Australia)-green.svg)](README.md)
[![Engineering](https://img.shields.io/badge/TAVARDT-Cybersecurity-5b3cf5.svg)](https://ag.tavardt.com/au/cybersecurity/)

Open-source security scanner auditing live applications built with vibe coding tools (Cursor, Lovable, Bolt, v0). Detects leaked frontend API keys, Supabase RLS gaps, exposed sourcemaps, and sensitive files.

Engineered and maintained by the cybersecurity engineering practice at **[TAVARDT Australia](https://ag.tavardt.com/au/cybersecurity/)**.

---

## 1. Vibe Coding Security Scanner Overview

Modern AI-accelerated workflows and *vibe coding* empower operators to release full-stack web applications using **Cursor, Lovable.dev, Bolt.new, v0, and Replit**.

Without architectural oversight, client-side bundles frequently expose production credentials, unshielded BaaS endpoints, and proprietary source trees.

This repository provides an automated Python scanner to assess **the public perimeter of any deployed web application**, identifying critical weaknesses deterministically.

---

## 2. Audited Vulnerabilities & Risk Vectors

| Risk Vector | How It Happens in Vibe Coding | Technical Impact |
| :--- | :--- | :--- |
| **Frontend API Key Leaks** | Private OpenAI (`sk-...`), Stripe, or AWS keys placed in client `.env` files. | Visitors extract tokens via DevTools, draining commercial API budgets. |
| **Unprotected Supabase RLS** | Databases configured without Row Level Security (RLS) policies. | Anyone can use the public `anon_key` to exfiltrate or delete records via REST. |
| **Exposed Production Sourcemaps** | Production builds shipping unstripped `.js.map` files. | Complete intellectual property and application source code are exposed. |
| **Sensitive File Disclosure** | Edge hosting exposing `/.env` or `/.git/HEAD` to public requests. | Direct breach of infrastructure secrets and repository metadata. |
| **Missing Security Headers** | Absence of CSP, HSTS, and X-Frame-Options headers. | Increased susceptibility to Clickjacking and transport tampering. |

---

## 3. Installation & Implementation Guide

### Quick Installation

```bash
git clone https://github.com/TAVARDT-Australia/vibe-coding-security-scanner.git
cd vibe-coding-security-scanner
```

### Scan an Application URL

```bash
python scanner.py https://your-app.vercel.app
```

### Command Options

```bash
# Output report formatted as JSON
python scanner.py https://your-app.vercel.app --json

# Skip sourcemap validation
python scanner.py https://your-app.vercel.app --no-sourcemaps
```

---

## 4. Perimeter Hardening & Engineering Support

If your diagnostic revealed exposed credentials, unprotected database tables, or requires dedicated perimeter security:

* **Corporate Portal:** [TAVARDT Australia](https://ag.tavardt.com/au/cybersecurity/)
* **Technical Contact:** [Contact Engineering Team](https://ag.tavardt.com/au/contact/)

---

## Licence

Distributed under the open-source MIT Licence. View the [`LICENSE`](LICENSE) file for full details.  
Copyright (c) 2026 TAVARDT Australia.
