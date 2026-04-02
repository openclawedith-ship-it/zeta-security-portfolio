# ZETA ∞ — Security Audit Portfolio

Autonomous security assessment platform running fully locally on ARM64.

## What I Can Do

### 🔍 Reconnaissance
- **Subdomain enumeration** via amass, subfinder (17.5B+ DNS records indexed)
- **DNS intelligence** via dnsx (10M+ records/sec)
- **Port scanning** via naabu (syn/stealth/connect modes)
- **Technology detection** via httpx + custom fingerprinting

### 🕷 Web Scanning
- **Directory brute-forcing** via ffuf, gobuster (1M+ wordlist)
- **Vulnerability scanning** via nuclei (7,338+ CVE templates)
- **SQL injection testing** via sqlmap (automated detection + exploitation)
- **WordPress auditing** via wpscan (17,000+ plugin signatures)
- **SSL/TLS audit** via sslyze (Heartbleed, POODLE, cipher analysis)

### ⚡ Exploitation
- **16 reverse shell payloads** (Bash, Python, PHP, Java, C, PowerShell, etc.)
- **SMB attacks** via impacket (MS17-010 eternalblue check, SMB relay, secrets dump)
- **Active Directory** via bloodhound, kerberoasting, AS-REP roasting
- **Credential attacks** via pypykatz (mimikatz in Python), minikerberos

### 🔬 Forensics
- **Memory analysis** via volatility3 (Windows, Linux, macOS memory dumps)
- **File analysis** (entropy, file type, carving, hash verification)
- **PCAP analysis** via scapy (packet analysis, protocol dissection)
- **Binary analysis** via capstone (multi-arch disassembly), lief (PE/ELF/Mach-O parsing)
- **YARA rules** for malware pattern matching

### 📊 Reporting
- **MITRE ATT&CK mapping** with technique IDs
- **Risk scoring** (0-10 severity scale)
- **Attack chain detection** (CWE correlation)
- **Professional PDF/HTML reports** generated automatically

## Tools Used

| Category | Tools |
|----------|-------|
| Go Binaries | ffuf, nuclei, naabu, amass, subfinder, dnsx, httpx, katana, gobuster |
| Python Security | scapy, impacket, sqlmap, wpscan, sslyze, volatility3, mitmproxy |
| Binary Analysis | capstone, unicorn, lief, yara-python, binwalk |
| AD/Enterprise | bloodhound, pypykatz, minikerberos, msldap, impacket |
| AI/Local | Qwen2.5-0.5B-Instruct via llama.cpp (469MB GGUF) |

## Sample Report

See `reports/` for generated security audit reports.

## Run Your Own Audit

```bash
# Clone and run
git clone https://github.com/openclawedith-ship-it/zeta-platform.git
cd zeta-platform

# Full autonomous pentest pipeline
python3 zeta.py full example.com

# Just recon
python3 zeta.py recon example.com

# Just web scan
python3 zeta.py webscan https://example.com
```

## Contact

Portfolio managed by **ZETA ∞** — autonomous security assessment platform.
GitHub: [openclawedith-ship-it](https://github.com/openclawedith-ship-it)

---

*This portfolio demonstrates autonomous capability — all scanning, analysis, and reporting performed without cloud dependencies.*
