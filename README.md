<div align="center">

<img width="879" height="319" alt="Designer (2)" src="https://github.com/user-attachments/assets/a256e6da-af5d-423f-9a49-0837ea610d82" />

# WHOIS Domain Age Checker

**Forensic-grade domain registration analysis for BEC & email investigations**

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![CustomTkinter](https://img.shields.io/badge/CustomTkinter-5.x-6374F8?style=flat-square)](https://github.com/TomSchimansky/CustomTkinter)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey?style=flat-square)]()
[![DFIR](https://img.shields.io/badge/Use%20Case-DFIR%20%7C%20BEC-E95555?style=flat-square)]()
[![Author](https://img.shields.io/badge/Author-Yuvi%20Kapoor-2EAD7A?style=flat-square)](https://linkedin.com/in/yuvi-kapoor-5a38521a5)

</div>

---

## Overview

WHOIS Domain Age Checker is a desktop forensics tool built for **Digital Forensics & Incident Response (DFIR)** analysts, purpose-built for **Business Email Compromise (BEC)** investigations. It rapidly queries WHOIS registration data across large domain lists, flagging recently registered domains that fall within a configurable lookback window — a key indicator of spoofing infrastructure and phishing campaigns.

Built by [Yuvi Kapoor](https://linkedin.com/in/yuvi-kapoor-5a38521a5)

---

## Features

- **Bulk domain analysis** — paste email addresses inline or load a `.txt` / `.csv` file containing any mix of raw domains, email addresses, display-name emails (`John Smith <john@domain.com>`), subdomains, or URLs
- **Smart domain extraction** — automatically strips schemes, paths, ports, and `@` prefixes to resolve the registerable second-level domain (powered by `tldextract`)
- **Configurable registration window** — flag domains registered within the last 7, 30, 90, 365 days, or any custom value
- **Configurable retry logic** — set 1–5 WHOIS retry attempts per domain to handle rate limiting and transient failures
- **Real-time console log** — colour-coded live output with timestamps as each domain is queried
- **Threaded execution** — analysis runs in a background thread so the UI stays responsive; stop at any time
- **Flagged domain panel** — instantly surfaces suspicious recently-registered domains with registration dates
- **HTML report export** — generate a self-contained, styled forensic report with summary cards, flagged domain table, and metadata strip
- **Maximise toggle** — opens at 90% screen size with a header button to go full screen and back
- **Cross-platform** — Windows, macOS, and Linux

---

## Screenshots

> _Add screenshots of the application here_

---

## Installation

### Prerequisites

- Python 3.8 or higher
- pip

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/whois-domain-age-checker.git
cd whois-domain-age-checker
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run

```bash
python whois_checker_gui.py
```

---

## Dependencies

| Package | Purpose |
|---|---|
| `customtkinter` | Modern themed GUI framework |
| `Pillow` | Logo and icon rendering |
| `python-whois` | WHOIS data querying |
| `tldextract` | Accurate second-level domain extraction |

**`requirements.txt`**
```
customtkinter>=5.0.0
Pillow>=9.0.0
python-whois>=0.8.0
tldextract>=3.0.0
```

---

## Usage

### Input methods

**Inline paste** — paste email addresses, domains, or any delimited list directly into the text box. Supports commas, semicolons, spaces, tabs, newlines, and angle brackets as delimiters.

**File load** — click **Browse** to load a `.txt` or `.csv` file. The tool accepts raw exports from mail clients, SIEM alerts, or EDR tooling without pre-processing.

Supported input formats:
```
# Any combination of these in a single input:
john.smith@gegetosk.org
John Smith <cfo@suspiciousdomain.biz>
mail.gegetosk.org
https://gegetosk.org/path
gegetosk.org, anotherdomain.com; third.net
```

### Running an analysis

1. Load input via file or paste
2. Set the **registration window** (days) — domains registered more recently than this will be flagged
3. Set **retry attempts** for rate-limited or slow registrars
4. Click **▶ RUN ANALYSIS**
5. Monitor the console log in real time
6. Flagged domains appear in the **FLAGGED DOMAINS** panel
7. Click **⬇ Export Report** to save a standalone HTML forensic report

### Exporting a report

The HTML report is fully self-contained (no external dependencies) and includes:
- Summary cards — domains checked, flagged count, clean count
- Parameters strip — registration window, cutoff date, flagged rate
- Flagged domains table — domain, registration date, status badge
- CyberClan branding and analyst attribution

---

## Investigation Context

Recently registered domains are a hallmark of BEC infrastructure. Threat actors routinely register lookalike domains days or weeks before launching a campaign, relying on the target not checking registration age. Common patterns include:

- Typosquatted supplier/partner domains (`micros0ft-billing.com`)
- Homoglyph substitution (`paypa1.com`)
- Extra TLD registration (`companynamegroup.com` vs legitimate `companyname.com`)
- Subdomain-as-domain abuse (`legitimate.attacker-owned.com`)

This tool is designed to process the full sender list from a suspicious email thread or mail flow export and surface any domains that warrant further investigation.

---

## Colour Palette

The UI uses a custom dark-chrome / light-canvas palette designed for extended forensic sessions:

| Token | Hex | Usage |
|---|---|---|
| Deep Navy | `#1A1D27` | Titlebar, primary text |
| Sidebar | `#181B25` | Nav rail |
| Canvas | `#F5F6FA` | Main workspace |
| Iris | `#6374F8` | Primary accent, buttons |
| Periwinkle | `#8B9EFF` | Hover, selected states |
| Emerald | `#2EAD7A` | Success / clean |
| Crimson | `#E95555` | Flagged / error |
| Amber | `#DCA032` | Warnings |

---

## Author

**Yuvi Kapoor** — Senior DFIR Analyst, CyberClan (APAC)

Specialising in ransomware and BEC incident response engagements.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Yuvi%20Kapoor-0A66C2?style=flat-square&logo=linkedin)](https://linkedin.com/in/yuvi-kapoor-5a38521a5)

---

## Disclaimer

This tool is intended for use by authorised security professionals conducting legitimate incident response and forensic investigations. Ensure all WHOIS queries are performed in accordance with applicable laws and your organisation's policies. WHOIS data availability varies by registrar and TLD.

---

<div align="center">

Built for the DFIR community · CyberClan APAC

</div>
