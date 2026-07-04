# OSINT Complete Reference & Cheatsheet

<p align="left">
  <img src="https://img.shields.io/badge/Level-Beginner%20to%20Advanced-blue?style=flat-square" alt="Level">
  <img src="https://img.shields.io/badge/Author-SigintRecon-black?style=flat-square" alt="Author">
  <img src="https://img.shields.io/badge/Framework-Open%20Source%20Intelligence-orange?style=flat-square" alt="Framework">
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="License">
  <img src="https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square" alt="Status">
</p>

**Maintained by:** [SigintRecon](https://github.com/sigintrecon)
**Scope:** Open Source Intelligence (OSINT) — structured methodology, tooling, and reference material for reconnaissance, digital forensics, and threat intelligence workflows.

---

## ⚠️ Legal & Ethical Warning

> This repository is built strictly for **educational purposes, authorized penetration testing, digital forensics, and threat intelligence**.
>
> Tracking, doxxing, or investigating individuals **without explicit consent** is illegal under Pakistan's **PECA 2016** (Prevention of Electronic Crimes Act) and applicable international cyber laws. Every technique documented here must only be applied within an authorized scope of engagement, a lawful investigation, or your own controlled lab environment.
>
> **Always operate ethically. Always operate within the law.**
>
> For the full legal notice — including relevant PECA provisions, international law considerations, and scope of use — see **[LEGAL.md](https://github.com/sigintrecon/osint-cheatsheet/blob/main/legal.md)**.

---

## Table of Contents

- [Repository Overview](#repository-overview)
- [The OSINT Intelligence Cycle](https://github.com/sigintrecon/osint-cheatsheet/edit/main/README.md#the-osint-intelligence-cycle)
- [Reference Modules](https://github.com/sigintrecon/osint-cheatsheet/edit/main/README.md#reference-modules-step-by-step-guides)
- [Core OSINT Frameworks Quick Directory](https://github.com/sigintrecon/osint-cheatsheet/edit/main/README.md#core-osint-frameworks-quick-directory)
- [Repository Structure](https://github.com/sigintrecon/osint-cheatsheet/edit/main/README.md#repository-structure)
- [Connect & Support](https://github.com/sigintrecon/osint-cheatsheet/edit/main/README.md#connect--support)

---

## Repository Overview

Welcome to the ultimate OSINT reference hub. This repository is structured into modular sections to help cybersecurity students, red teamers, and investigators navigate public data collection effectively — from foundational concepts to advanced, tool-driven workflows.

---

## The OSINT Intelligence Cycle

To produce actionable intelligence, follow this structured workflow:

| Phase | Description | Example Action |
|---|---|---|
| **1. Requirements** | Defining what you need to find. | "Find all leaked corporate emails of target.com" |
| **2. Collection** | Gathering raw data from public sources. | Running automated scrapers or Google Dorks. |
| **3. Processing** | Organizing raw data into a readable format. | Cleaning duplicate data, sorting emails alphabetically. |
| **4. Analysis** | Connecting the dots to find vulnerabilities. | Identifying that a specific developer leaks API keys. |
| **5. Dissemination** | Presenting findings to stakeholders/clients. | Writing the final assessment/Red Team report. |

> 💡 **Why this matters:** Skipping straight to "collection" without defined requirements is the #1 mistake beginners make — it produces noise, not intelligence. Every phase after collection exists to turn raw data into something a decision-maker can act on.

---

## Reference Modules (Step-by-Step Guides)

### 1. Operational Security (OPSEC)

Never investigate from your personal infrastructure. Follow the **Sock Puppet** rule:

- Use a hardened, privacy-tuned browser (Brave / Firefox).
- Always route traffic via a trustworthy **VPN** or the **Tor Network**.
- Separate your digital identity using dedicated **Virtual Machines** (e.g., CSI Linux).

### 2. Advanced Web Intelligence

Deep dive into search engine manipulation to find exposed logs, credentials, and databases.
👉 [Read the Advanced Google Dorking Guide](https://github.com/sigintrecon/osint-cheatsheet/blob/main/google-dorking.md)

### 3. Technical & CLI OSINT Tools

Automated workflows using command-line interface tools to extract subdomains, emails, and target data.
👉 [Read the CLI OSINT Tools & Configuration Guide](https://github.com/sigintrecon/osint-cheatsheet/blob/main/cli-osint-tools.md)

### 4. Geolocation & Imagery OSINT

Analyzing visual data to locate physical coordinates:

- **EXIF Data:** Extract hidden metadata using `exiftool target.jpg`.
- **Visual Landmarks:** Analyze architecture, street signs, power poles, and vehicle registration plates to isolate geographic regions.
- **Cross-referencing:** Validate imagery using Google Earth Pro satellite tracking.

---

## Core OSINT Frameworks Quick Directory

| Source / Tool | Type | Core Utility |
|---|---|---|
| **[OSINT Framework](https://osintframework.com)** | Web Directory | Complete map of public OSINT resources. |
| **IntelX / DeHashed** | Breach Database | Tracking leaked passwords, pastebins, and historic data breaches. |
| **[HaveIBeenPwned](https://haveibeenpwned.com)** | Verification | Check if a target email has been compromised globally. |
| **Maltego** | Desktop GUI | Graphical link analysis and entity relationship mapping. |

---

## Repository Structure

```
osint-reference-cheatsheet/
├── README.md
├── modules/
│   ├── google-dorking.md        # Advanced search engine reconnaissance
│   └── cli-osint-tools.md       # Automated CLI footprinting workflows
└── references/
    └── sources.md               # Consolidated citation list
```

---

## Connect & Support

- **GitHub Profile:** [github.com/sigintrecon](https://github.com/sigintrecon)

---

Distributed under the **MIT License**. See [LICENSE](https://github.com/sigintrecon/osint-cheatsheet/blob/main/LICENSE) for details.

<p align="center">
  <sub>Built and maintained by <a href="https://github.com/sigintrecon">SigintRecon</a> — part of a structured path toward Red Team Operations.</sub>
</p>
