# CLI OSINT Tools & Automation Workflows 🛠️

### Automated Footprinting & Command-Line Target Profiling
**Part of the OSINT Cheatsheet Series by [SigintRecon](https://github.com/sigintrecon)**

---

Automating data collection prevents analyst fatigue, accelerates passive reconnaissance, and structured log extraction during red team engagements. Below are the production workflows for industry-standard open-source command-line intelligence tools.

---

## 1. Username Enumeration (Sherlock Framework)
The Sherlock tool hunts down specific username handles across 350+ social networks and digital platforms simultaneously to map out a target's online presence.

### Installation & System Setup
```bash
# Clone the official source repository from GitHub
git clone [https://github.com/sherlock-project/sherlock.git](https://github.com/sherlock-project/sherlock.git)
cd sherlock

# Install python dependencies required for concurrent requests
pip3 install -r requirements.txt

