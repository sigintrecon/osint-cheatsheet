# 🔍 Advanced Google Dorking Reference Guide

<p align="left">
  <img src="https://img.shields.io/badge/Module-Web%20Intelligence-blue?style=flat-square" alt="Module">
  <img src="https://img.shields.io/badge/Level-Intermediate-orange?style=flat-square" alt="Level">
</p>

**Open Source Intelligence & Search Engine Manipulation**
Part of the [OSINT Cheatsheet Series](https://github.com/sigintrecon/osint-cheatsheet) by [SigintRecon](https://github.com/sigintrecon)

> ⚠️ **Reminder:** Every dork in this guide is intended for **authorized reconnaissance** — bug bounty scope, sanctioned red team engagements, or your own infrastructure. Running these against unauthorized targets is illegal. See the [main legal notice](../README.md#-legal--ethical-warning).

Google Dorking (also known as Google Hacking) involves using advanced search operators to filter through Google's massive index to uncover security misconfigurations, exposed sensitive files, credentials, and open administration panels that should never have been publicly accessible.

---

## Table of Contents

- [Core Dorking Operators Reference](#1-core-dorking-operators-reference)
- [Real-World Penetration Testing Dorks](#2-real-world-penetration-testing-dorks)
- [Best Practices](#-best-practices)

---

## 1. Core Dorking Operators Reference

| Operator | Syntax Examples | Purpose / Description |
|---|---|---|
| `site:` | `site:gov.pk` | Restricts the search results strictly to a specific domain, subdomain, or Top-Level Domain (TLD). |
| `filetype:` | `filetype:env` / `filetype:sql` | Filters results to display only specific file extensions (e.g., `pdf`, `log`, `xml`, `xlsx`). |
| `intitle:` | `intitle:"index of"` | Searches for specific strings or keywords located inside the website's HTML `<title>` tag. |
| `inurl:` | `inurl:admin/login.php` | Restricts results to URLs that contain the specified string or folder path anywhere in the web address. |
| `intext:` | `intext:"wpa_supplicant"` | Forces Google to show pages that contain the specific string explicitly within the visible body text. |
| `cache:` | `cache:target.com` | Displays Google's cached historical view of a webpage (useful if the page was recently taken down). |

---

## 2. Real-World Penetration Testing Dorks

These dorks are used during the **passive reconnaissance phase** of a red team assessment or bug bounty target evaluation.

### A. Information Leakage & Environment Configurations

Web frameworks often store sensitive deployment configurations and API secret tokens in plaintext files. If bad directory permissions exist, these can be leaked.

```
# Exposes Laravel/PHP environment configuration files containing plaintext DB & SMTP passwords
filetype:env "DB_PASSWORD"

# Locates exposed WordPress configuration file backups containing database salt keys
filetype:bak inurl:wp-config

# Finds public Git configuration folders containing source control metadata and access tokens
inurl:"/.git" intitle:"Index of /"
```

### B. Open Directories & Exposed Admin Panels

```
# Finds open directory listings that expose raw server contents
intitle:"index of /" "parent directory"

# Locates exposed administrator login portals across various CMS platforms
inurl:admin intitle:"login"
```

### C. Exposed Documents & Sensitive File Types

```
# Finds publicly indexed spreadsheets that may contain internal data
filetype:xlsx inurl:internal

# Finds exposed log files that can reveal internal paths, errors, or credentials
filetype:log inurl:"error_log"
```

---

## Best Practices

- **Stay in scope.** Only run these dorks against domains you are explicitly authorized to test.
- **Document everything.** Screenshot and log the exact dork used and the timestamp — this matters for your final report.
- **Verify before reporting.** A dork surfacing a result doesn't confirm exploitability — always validate the finding responsibly before disclosure.
- **Practice responsible disclosure.** If you stumble across a real, live exposure outside an authorized engagement, report it through the organization's official disclosure channel — never exploit or exfiltrate data.

---

## Related Modules

- [CLI OSINT Tools & Automation Workflows](cli-osint-tools.md)
- [Back to Main README](https://github.com/sigintrecon/osint-cheatsheet/blob/main/README.md)
