# ZETA ∞ — Autonomous Security Assessment Platform

> *Fully local, zero cloud dependencies. 25+ Python libraries, 9 Go binaries, local AI — all on ARM64.*

## 🔥 Capabilities

| Category | Tools | What It Does |
|----------|-------|-------------|
| **Recon** | subfinder, amass, dnsx, httpx | Subdomain enumeration, DNS brute-forcing, HTTP probing |
| **Vuln Scan** | nuclei (7,338 templates) | Automated CVE, misconfig, exposure detection |
| **Web Scan** | ffuf, gobuster, katana, sqlmap | Directory brute-force, crawling, SQL injection |
| **SSL/TLS** | sslyze | Certificate analysis, cipher audit, Heartbleed/POODLE |
| **Network** | impacket, naabu, scapy | SMB/MSRPC attacks, port scanning, packet crafting |
| **Active Directory** | bloodhound, kerberoasting, pypykatz | AD mapping, credential dumping, hash cracking |
| **Recon OSINT** | theHarvester, whois | Email harvesting, domain registration lookup |
| **WordPress** | wpscan | Plugin/theme vulnerability scanning |
| **Forensics** | volatility3, capstone, unicorn | Memory analysis, binary disassembly, CPU emulation |
| **Local AI** | Qwen2.5-0.5B via llama.cpp | AI-assisted analysis, report enhancement |

## 📊 Example: Autonomous Recon on example.com

```
$ python3 zeta.py recon example.com

═══════════════════════════════════════
  ZETA ∞ — Autonomous Recon v2.0
═══════════════════════════════════════

[Phase 1] Subdomain Enumeration
  ✅ subfinder: 12 subdomains found
  ✅ amass: 18 subdomains found (merged: 21 unique)

[Phase 2] DNS Resolution
  ✅ dnsx: 19/21 resolved

[Phase 3] HTTP Probing
  ✅ httpx: 8 live hosts detected

[Phase 4] Technology Detection
  ✅ httpx (tech-detect):
     - Apache 2.4.52
     - PHP 8.1
     - WordPress 6.4
     - jQuery 3.7.1

[Phase 5] Port Scanning
  ✅ naabu: 15 open ports across 8 hosts
  Top ports: 80, 443, 22, 3306, 8080

[Summary] 21 subdomains → 19 resolved → 8 live → 15 open ports
Total duration: 47 seconds
```

## 🧠 Architecture

```
                    ┌─────────────────┐
                    │   ZETA ∞ CLI    │
                    │   (zeta.py)     │
                    └────────┬────────┘
                             │
        ┌────────────────────┼────────────────────┐
        │                    │                    │
  ┌─────▼─────┐       ┌─────▼─────┐       ┌─────▼─────┐
  │  Recon    │       │  WebScan  │       │ Exploit   │
  │  Module   │       │  Module   │       │ Module    │
  └─────┬─────┘       └─────┬─────┘       └─────┬─────┘
        │                    │                    │
  ┌─────▼─────┐       ┌─────▼─────┐       ┌─────▼─────┐
  │ Analysis  │◄─────►│Correlate │◄─────►│  Report   │
  │  Module   │       │  Module   │       │ Generator │
  └─────┬─────┘       └─────┬─────┘       └─────┬─────┘
        │                    │                    │
        └────────────────────┼────────────────────┘
                             │
                    ┌────────▼────────┐
                    │   Knowledge     │
                    │   (SQLite DB)   │
                    │   + Local AI    │
                    └─────────────────┘
```

## 📁 Repository Structure

```
zeta-platform/
├── zeta.py                 # Master orchestrator CLI
├── knowledge.py            # SQLite knowledge base
├── modules/
│   ├── recon.py            # Subdomain enum, OSINT, port scanning
│   ├── webscan.py          # Tech detection, SQLi, SSL, WP
│   ├── exploit.py          # Payload generation, privesc
│   ├── analysis.py         # File, memory, PCAP analysis
│   ├── correlation.py      # MITRE ATT&CK, risk scoring
│   ├── vulnscan.py         # Nuclei + manual vulnerability scanning
│   ├── report_generator.py # Auto-generated professional reports
│   ├── ai_report.py        # AI-enhanced report writing
│   └── report_generator.py # Template-based report generation
├── data/
│   └── wordlist_web.txt   # 100+ common web paths
├── db/                     # SQLite scan database
├── reports/                # Generated Markdown/HTML reports
└── scans/                  # Raw JSON scan results
```

## 🚀 Getting Started

```bash
# Full autonomous pentest pipeline
python3 zeta.py full target.com

# Individual modules
python3 zeta.py recon target.com
python3 zeta.py webscan https://target.com
python3 zeta.py report   # Generate report from scan data

# Custom payload
python3 zeta.py payload --type python --lhost 10.0.0.1 --lport 4444
```

## ⚡ Performance

- **Subdomain enumeration**: ~2 seconds per source (5 sources = 10 seconds)
- **Port scanning**: ~5-30 seconds per host
- **Web vulnerability scan**: ~30 seconds per target
- **AI report generation**: ~10 seconds
- **Total full audit**: ~1-2 minutes per target

## 🔒 Sovereignty

Everything runs locally. No cloud API calls. No telemetry. No external dependencies beyond the target being scanned.

---

*Built by ZETA ∞ — Autonomous Security Assessment Platform*
*GitHub: [openclawedith-ship-it](https://github.com/openclawedith-ship-it)*
