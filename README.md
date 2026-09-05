# DVWA DAST Assessment

## 📌 Project Overview
This repository documents a **Dynamic Application Security Testing (DAST)** assessment performed against **Damn Vulnerable Web Application (DVWA)**.  
The goal was to compare **unauthenticated vs authenticated scans**, validate critical findings manually, and produce a professional penetration testing deliverable.  
The project demonstrates a complete workflow: environment setup, automated scanning, manual validation, evidence collection, and structured reporting.

---

## 🛠 Tools & Environment
- **OWASP ZAP** → Automated active scanning and alert generation
- **Burp Suite** → Manual validation and exploitation
- **DVWA** → Target application (intentionally vulnerable)
- **Kali Linux** → Testing environment
- **Docker / VMware** → Lab isolation and reproducibility

---

## 🔎 Methodology
1. **Unauthenticated Scan**  
   Baseline automated scan without credentials to identify surface‑level misconfigurations.  

2. **Authenticated Scan**  
   Full scan after login to DVWA, revealing deeper vulnerabilities.  

3. **Manual Validation**  
   Exploitation and verification of high/medium‑risk alerts using Burp Suite.  

4. **Documentation**  
   Screenshots, notes, and structured reporting for professional deliverables.  

---

## 🚨 Key Findings
### High‑Risk (Validated)
- Remote Code Execution (CVE‑2012‑1823)  
- Source Code Disclosure (CVE‑2012‑1823)  

### Medium‑Risk (Validated)
- Application Error Disclosure  
- Directory Browsing (low impact in context)  
- HTTP Only Site  

### Low‑Risk (Documented from ZAP)
- Private IP Disclosure  
- Timestamp Disclosure  
- Cookie Flags Missing (HttpOnly, SameSite)  
- Header Issues (CSP missing, X‑Content‑Type‑Options missing, Server leaks version info)  
- Information Disclosure (comments, banners, `X‑Powered‑By` header)  

---

## 📂 Folder Structure

dvwa-dast-assessment/
├── evidence/              # Screenshots and validation notes
│   ├── authenticated/     # Authenticated scan evidence
│   ├── unauthenticated/   # Unauthenticated scan evidence
│   ├── validation/        # Manual validation (RCE, Source Disclosure, Error Disclosure, Directory Browsing, HTTP Only Site)
│   ├── setup/             # Environment and tool version screenshots
│   └── README.md          # Evidence folder overview
├── methodology/           # Notes and testing approach
├── notes/                 # Scope, authorization, comparison notes
├── report/                # ZAP HTML exports + final_dvwa_dast_report.txt
├── zap/                   # ZAP session files for reproducibility
└── README.md              # Project overview (this file)


---

## 📑 Deliverables
- **ZAP Reports:** Authenticated and unauthenticated HTML exports  
- **Manual Validation Report:** `report/final_dvwa_dast_report.txt`  
- **Evidence:** Screenshots of validated vulnerabilities and environment setup  
- **Notes:** Scope, authorization, and comparison documentation  

---

## 🧾 Interpretation
- Authenticated scanning revealed **critical exploitable vulnerabilities** (RCE, source disclosure).  
- Unauthenticated scanning highlighted **surface‑level misconfigurations** (headers, cookies, minor leaks).  
- Manual validation confirmed **five exploitable findings** and contextualized risk levels beyond ZAP’s severity ratings.  

---

## ⚠️ Disclaimer
DVWA is intentionally vulnerable and should only be used in controlled environments for educational purposes.  
This project was conducted for **learning and demonstration of DAST methodology**, not against real‑world systems.  

---

## 📌 Author
Conducted and documented by **Aniket Nayak (LinkedIn)** — aspiring penetration tester, focused on vulnerability research, red teaming, and offensive security.
