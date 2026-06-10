# OSINT Complete Reference & Cheatsheet 

### Beginner to Advanced | Open Source Intelligence Framework
**Maintained by: [SigintRecon](https://github.com/sigintrecon)**

---

> **LEGAL & ETHICAL WARNING:** This repository is built strictly for educational purposes, authorized penetration testing, digital forensics, and threat intelligence. Tracking, doxxing, or investigating individuals without explicit consent is illegal under Pakistan's **PECA 2016** (Prevention of Electronic Crimes Act) and international cyber laws. Always operate ethically.

---

## Repository Overview
Welcome to the ultimate OSINT reference hub. This repository is structured into modular sections to help cybersecurity students, red teamers, and investigators navigate public data collection effectively.

### The OSINT Intelligence Cycle
To produce actionable intelligence, follow this structured workflow:

| Phase | Description | Example Action |
| :--- | :--- | :--- |
| **1. Requirements** | Defining what you need to find. | "Find all leaked corporate emails of target.com" |
| **2. Collection** | Gathering raw data from public sources. | Running automated scrapers or Google Dorks. |
| **3. Processing** | Organizing raw data into a readable format. | Cleaning duplicate data, sorting emails alphabetically. |
| **4. Analysis** | Connecting the dots to find vulnerabilities. | Identifying that a specific developer leaks API keys. |
| **5. Dissemination** | Presenting findings to stakeholders/clients. | Writing the final assessment/Red Team report. |

---

## Reference Modules (Step-by-Step Guides)

### 1. Operational Security (OPSEC)
Never investigate from your personal infrastructure. Follow the **Sock Puppet** rule:
* Use a hardened browser (Brave/Firefox privacy tuned).
* Always route traffic via a trustworthy VPN or the Tor Network.
* Separate your digital identity using dedicated Virtual Machines (e.g., CSI Linux).

### 2. Advanced Web Intelligence
Deep dive into search engine manipulation to find exposed logs, credentials, and databases.
* 👉 **[Read the Advanced Google Dorking Guide](google-dorking.md)**

### 🛠️ 3. Technical & CLI OSINT Tools
Automated workflows using command-line interface tools to extract subdomains, emails, and target data.
* 👉 **[Read the CLI OSINT Tools & Configuration Guide](cli-osint-tools.md)**

### 4. Geolocation & Imagery OSINT
Analyzing visual data to locate physical coordinates:
* **EXIF Data:** Extract hidden metadata using `exiftool target.jpg`.
* **Visual Landmarks:** Analyze architecture, street signs, power poles, and car registration plates to isolate geographic regions.
* Cross-reference imagery using **Google Earth Pro** satellite tracking.

---

## Core OSINT Frameworks Quick Directory

| Source / Tool | Type | Core Utility |
| :--- | :--- | :--- |
| **OSINT Framework** | Web Directory | Complete map of public OSINT resources (`osintframework.com`). |
| **IntelX / DeHashed** | Breach Database | Tracking leaked passwords, pastebins, and historic data breaches. |
| **HaveIBeenPwned** | Verification | Check if a target email has been compromised globally. |
| **Maltego** | Desktop GUI | Graphical link analysis and entity relationship mapping. |

---
**Connect & Support**
* **GitHub Profile:** [github.com/sigintrecon](https://github.com/sigintrecon)
* **TryHackMe:** [tryhackme.com/p/sigintrecon](https://tryhackme.com/p/sigintrecon)

*Distributed under the MIT License. See `LICENSE` for details.*
