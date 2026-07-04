# 🛠️ CLI OSINT Tools & Automation Workflows

<p align="left">
  <img src="https://img.shields.io/badge/Module-Technical%20OSINT-blue?style=flat-square" alt="Module">
  <img src="https://img.shields.io/badge/Level-Intermediate-orange?style=flat-square" alt="Level">
</p>

**Automated Footprinting & Command-Line Target Profiling**
Part of the [OSINT Cheatsheet Series](../README.md) by [SigintRecon](https://github.com/sigintrecon)

> ⚠️ Only run these tools against targets you are explicitly authorized to assess. See the [main legal notice](../README.md#-legal--ethical-warning).

Automating data collection prevents analyst fatigue, accelerates passive reconnaissance, and enables structured log extraction during red team engagements. Below are production workflows for industry-standard, open-source command-line intelligence tools.

---

## Table of Contents

- [Username Enumeration (Sherlock)](#1-username-enumeration-sherlock-framework)
- [Email & Subdomain Harvesting (theHarvester)](#2-email--subdomain-harvesting-theharvester)
- [Subdomain Discovery (Subfinder)](#3-subdomain-discovery-subfinder)
- [Workflow Tips](#-workflow-tips)

---

## 1. Username Enumeration (Sherlock Framework)

The **Sherlock** tool hunts down specific username handles across 350+ social networks and digital platforms simultaneously to map out a target's online presence.

### Installation & System Setup

```bash
# Clone the official source repository from GitHub
git clone https://github.com/sherlock-project/sherlock.git
cd sherlock

# Install python dependencies required for concurrent requests
pip3 install -r requirements.txt
```

### Basic Usage

```bash
# Search for a single username across all supported platforms
python3 sherlock.py target_username

# Search multiple usernames in one run
python3 sherlock.py username_one username_two

# Save results to a specific output folder
python3 sherlock.py target_username --output ./results/
```

### Notes

- Sherlock only checks for the **existence** of an account tied to a username — it does not access private data or bypass authentication.
- Cross-reference results manually; false positives can occur on platforms with generic "account not found" page structures.

---

## 2. Email & Subdomain Harvesting (theHarvester)

**theHarvester** aggregates emails, subdomains, hostnames, and employee names from public sources (search engines, PGP key servers, and certificate transparency logs).

### Installation

```bash
git clone https://github.com/laramies/theHarvester.git
cd theHarvester
pip3 install -r requirements/base.txt
```

### Basic Usage

```bash
# Harvest emails and subdomains for a target domain using Google as the source
python3 theHarvester.py -d target.com -b google

# Use multiple sources at once for broader coverage
python3 theHarvester.py -d target.com -b google,bing,crtsh
```

### Notes

- `-b all` queries every supported source but is slower and more likely to hit rate limits.
- Certificate transparency logs (`crtsh`) are one of the highest-signal, lowest-noise sources for subdomain discovery.

---

## 3. Subdomain Discovery (Subfinder)

**Subfinder** is a fast, passive subdomain enumeration tool that queries multiple public data sources without directly touching the target's infrastructure.

### Installation

```bash
git clone https://github.com/projectdiscovery/subfinder.git
```

### Basic Usage

```bash
# Enumerate subdomains for a target domain
subfinder -d target.com

# Save output to a file for further processing
subfinder -d target.com -o subdomains.txt

# Chain with httpx to check which discovered subdomains are live
subfinder -d target.com | httpx -silent
```

### Notes

- Being fully passive, Subfinder is a safe first step in any authorized recon workflow — it never sends probes directly to target-owned infrastructure.
- Combine with `httpx` or `nmap` (from your `network-enum` repo) for active validation once subdomains are confirmed in scope.

---

## Workflow Tips

- **Automate, then verify.** CLI tools are excellent for speed, but every finding should be manually reviewed before it goes into a report.
- **Rate-limit yourself.** Aggressive automated querying can trigger WAF/IDS alerts even during passive recon — pace your requests.
- **Log everything.** Save raw tool output before processing/filtering it, so your evidence trail remains intact for the final report.
- **Combine tools.** The real value comes from chaining: Subfinder → httpx → theHarvester → manual verification, not relying on any single tool in isolation.

---

## Related Modules

- [Advanced Google Dorking Reference Guide](google-dorking.md)
