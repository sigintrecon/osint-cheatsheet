# Advanced Google Dorking Reference Guide

### Open Source Intelligence & Search Engine Manipulation
**Part of the OSINT Cheatsheet Series by [SigintRecon](https://github.com/sigintrecon)**

---

Google Dorking (also known as Google Hacking) involves using advanced search operators to filter through Google's massive index to uncover security misconfigurations, exposed sensitive files, credentials, and open administration panels that should never have been publicly accessible.

---

## 1. Core Dorking Operators Reference

| Operator | Syntax Examples | Purpose / Description |
| :--- | :--- | :--- |
| `site:` | `site:gov.pk` | Restricts the search results strictly to a specific domain, subdomain, or Top-Level Domain (TLD). |
| `filetype:` | `filetype:env` / `filetype:sql` | Filters results to display only specific file extensions (e.g., pdf, log, xml, xlsx). |
| `intitle:` | `intitle:"index of"` | Searches for specific strings or keywords located inside the website's HTML `<title>` tag. |
| `inurl:` | `inurl:admin/login.php` | Restricts results to URLs that contain the specified string or folder path anywhere in the web address. |
| `intext:` | `intext:"wpa_supplicant"` | Forces Google to show pages that contain the specific string explicitly within the visible body text. |
| `cache:` | `cache:target.com` | Displays Google's cached historical view of a webpage (useful if the page was recently taken down). |

---

## 2. Real-World Penetration Testing Dorks

These dorks are used during the passive reconnaissance phase of a red team assessment or bug bounty target evaluation.

### A. Information Leakage & Environment Configurations
Web frameworks often store sensitive deployment configurations and API secret tokens in plaintext files. If bad directory permissions exist, these can be leaked.

```text
# Exposes Laravel/PHP environment configuration files containing plaintext DB & SMTP passwords
filetype:env "DB_PASSWORD"

# Locates exposed WordPress configuration file backups containing database salt keys
filetype:bak inurl:wp-config

# Finds public Git configuration folders containing source control metadata and access tokens
inurl:"/.git" intitle:"Index of /"
