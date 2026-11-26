
<div align="center">

# ⚡ MEDIROZA GENERAL HOSPITAL
### PENETRATION TESTING REPORT

<img src="https://img.shields.io/badge/NETWORKWALKS-CYBERSECURITY-00FF88?style=for-the-badge&labelColor=080808" />
<img src="https://img.shields.io/badge/PROJECT-WEEK_04-00D9FF?style=for-the-badge&labelColor=080808" />
<img src="https://img.shields.io/badge/STATUS-COMPLETED-00FF88?style=for-the-badge&labelColor=080808" />

**RECONNAISSANCE • NETWORK SECURITY • WEB APPLICATION SECURITY • PDF SECURITY**

*Learning by Testing. Securing by Understanding.*

</div>

---

## 🟢 `01` — PROJECT OVERVIEW

This repository documents a penetration-testing assessment of **Mediroza General Hospital**, conducted as part of the NetworkWalks Cybersecurity Program, Batch B084.

The assessment followed a structured, six-phase black-box testing methodology, focusing on the target website's publicly accessible resources, network services, web application functionality, authentication mechanisms, PDF document protection, and potential information exposure.

The project involved reconnaissance, network and service identification, web application investigation, authentication testing, PDF security analysis, and information exposure investigation.

The objective was to identify potential security weaknesses, collect supporting evidence, assess associated risks, and provide recommendations for improving the security of the target web application.

---

## 🖥️ `02` — PROJECT INFORMATION

| Category | Details |
|:---|:---|
| **Project** | Mediroza General Hospital |
| **Organization** | NetworkWalks |
| **Program** | Cybersecurity Program |
| **Batch** | B084-Networkwalks |
| **Project Week** | Week 04 |
| **Report Reference** | W4-PM-FINAL |
| **Assessment Type** | Black-Box Penetration Testing |
| **Target** | `https://medirozahospital.com` |
| **Environment** | Kali Linux |
| **Authorization** | Written authorization secured directly from the client |
| **Modules Completed** | W4-M1, W4-M2, W4-M3 |
| **Assessment Period** | Five days |
| **Report Date** | 27 November 2026 |
| **Author** | Muhammed Irfan |

---

## 🔍 `03` — ASSESSMENT METHODOLOGY

The assessment followed six sequential phases:

### PHASE 01 — RECONNAISSANCE AND FOOTPRINTING

- Domain information gathering using WHOIS
- DNS enumeration and record analysis
- Website technology fingerprinting
- HTTP response observation
- Robots.txt inspection
- Sitemap analysis
- Public website structure and link analysis
- Identification of patient and staff login interfaces
- Legacy interface identification

### PHASE 02 — NETWORK AND SERVICE IDENTIFICATION

- Target IP identification
- Network scanning
- Open-port identification
- Service identification
- Service-version detection
- Network exposure documentation
- Review of externally visible services

### PHASE 03 — WEB APPLICATION INVESTIGATION

- Website structure investigation
- Publicly accessible page inspection
- HTTP response-header analysis
- Authentication endpoint identification
- Browser Developer Tools inspection
- Identification of missing security response headers
- Legacy interface accessibility observation

### PHASE 04 — AUTHENTICATION TESTING

- Patient login interface investigation
- Controlled authentication testing
- SQL injection-related login testing
- Application response analysis
- Patient portal behaviour observation
- Documentation of preliminary authentication findings

### PHASE 05 — PDF DOCUMENT SECURITY ANALYSIS

- Analysis of three patient report PDF documents
- Encryption status verification
- PDF hash extraction
- Password recovery analysis
- John the Ripper usage
- Password verification against original documents
- Documentation of PDF password-protection weaknesses

### PHASE 06 — INFORMATION EXPOSURE INVESTIGATION

- Investigation of publicly accessible organizational information
- Staff-related information exposure observation
- Shareholder-related information exposure observation
- Documentation of potential confidentiality impact
- Evidence-based assessment of information exposure

---

## 🛠️ `04` — TOOLS AND TECHNOLOGIES

The following tools and technologies are documented in the final assessment report.

<div align="center">

<img src="https://img.shields.io/badge/KALI_LINUX-557C94?style=for-the-badge&logo=kalilinux&logoColor=white" />
<img src="https://img.shields.io/badge/WHOIS-555555?style=for-the-badge" />
<img src="https://img.shields.io/badge/WHATWEB-00A86B?style=for-the-badge" />
<img src="https://img.shields.io/badge/NMAP-214478?style=for-the-badge" />
<img src="https://img.shields.io/badge/CURL-073551?style=for-the-badge&logo=curl&logoColor=white" />
<img src="https://img.shields.io/badge/DNS_UTILITIES-008080?style=for-the-badge" />
<img src="https://img.shields.io/badge/JOHN_THE_RIPPER-8B0000?style=for-the-badge" />

</div>

| Tool | Purpose |
|:---|:---|
| Kali Linux | Operating system used for penetration-testing activities |
| WHOIS | Domain registration information gathering |
| WhatWeb | Website technology fingerprinting |
| DNS utilities (nslookup/dig) | DNS record resolution and infrastructure identification |
| cURL (`curl -I`) | HTTP response-header analysis |
| Nmap | Network scanning and service identification |
| Web Browser / Developer Tools | Manual inspection of website structure, links and login interfaces |
| John the Ripper | Password analysis on extracted PDF hashes |
| Hash Extractor | Extraction of password hashes from encrypted PDF documents |

---

## 🚨 `05` — SECURITY FINDINGS

The assessment documented five security findings.

| Finding ID | Finding | Risk Classification |
|:---|:---|:---|
| W4-F01 | Suspected SQL Injection Authentication Bypass | Preliminary High |
| W4-F02 | Missing Security Response Headers | Low–Medium |
| W4-F03 | Accessible Legacy `/old/` Interface | Low–Medium |
| W4-F04 | PDF Password Protection Weakness | High – Confirmed |
| W4-F05 | Potential Exposure of Staff/Shareholder Information | Medium |

### FINDING HIGHLIGHTS

**W4-F01 — Suspected SQL Injection Authentication Bypass**

A controlled input submitted through the patient login interface resulted in navigation to an apparent patient portal. The observed behaviour is consistent with a possible authentication bypass. However, the underlying SQL query and backend mechanism were not independently confirmed. The finding remains preliminary and requires further validation.

**W4-F02 — Missing Security Response Headers**

The captured HTTP response did not include the following recommended security headers:

- Content-Security-Policy (CSP)
- HTTP Strict-Transport-Security (HSTS)
- X-Content-Type-Options
- Referrer-Policy

**W4-F03 — Accessible Legacy `/old/` Interface**

An accessible legacy interface was identified during reconnaissance. Its accessibility was documented, but no detailed content or functionality assessment was performed.

**W4-F04 — PDF Password Protection Weakness**

All three tested PDF documents were encrypted, and their passwords were successfully recovered using offline password-analysis techniques. This is the confirmed finding with a High risk rating.

**W4-F05 — Potential Exposure of Staff/Shareholder Information**

Staff and shareholder-related information was observed to be accessible during the assessment. The access path was not established as fully reproducible, and the finding was classified as Medium.

> **Important:** All patient, staff and shareholder records used in this assessment were fictional lab data. The findings and their limitations are documented in the final report.

---

## 📊 `06` — RISK ANALYSIS

| Finding ID | Likelihood | Impact | Overall Risk |
|:---|:---|:---|:---|
| W4-F04 | High | High | 🔴 High |
| W4-F01 | High | High | 🔴 High |
| W4-F05 | Medium | Medium | 🟡 Medium |
| W4-F02 | Medium | Low–Medium | 🟡 Low–Medium |
| W4-F03 | Low–Medium | Low–Medium | 🟡 Low–Medium |

The confirmed PDF password-protection weakness represents the highest-confidence risk identified during the assessment. The suspected authentication bypass remains a high-priority preliminary finding pending further validation.

---

## 📸 `07` — EVIDENCE DOCUMENTATION

This repository includes **13 screenshots** documenting the assessment activities and supporting the findings presented in the final report.

| Evidence File | Description |
|:---|:---|
| [01-network-service-port-scan.png](01-network-service-port-scan.png) | Network scanning and detected services |
| [02-recon-robots-txt.png](02-recon-robots-txt.png) | Robots.txt inspection |
| [03-recon-legacy-page.png](03-recon-legacy-page.png) | Accessible legacy interface |
| [04-info-staff-shareholder-exposure.png](04-info-staff-shareholder-exposure.png) | Staff and shareholder information exposure observation |
| [05-auth-sql-injection-login-attempt.png](05-auth-sql-injection-login-attempt.png) | Controlled authentication test input |
| [06-auth-patient-portal-result.png](06-auth-patient-portal-result.png) | Observed patient portal response |
| [07-pdf1-hash-generation.png](07-pdf1-hash-generation.png) | First PDF hash generation |
| [08-pdf1-password-cracking.png](08-pdf1-password-cracking.png) | First PDF password recovery |
| [09-pdf1-password-verification.png](09-pdf1-password-verification.png) | First PDF password verification |
| [10-pdf2-password-cracking.png](10-pdf2-password-cracking.png) | Second PDF password recovery |
| [11-pdf2-password-verification.png](11-pdf2-password-verification.png) | Second PDF password verification |
| [12-pdf3-jtr-password-cracking.png](12-pdf3-jtr-password-cracking.png) | Third PDF password recovery using John the Ripper |
| [13-pdf3-password-verification.png](13-pdf3-password-verification.png) | Third PDF password verification |

---

## 📄 `08` — FINAL PENETRATION TESTING REPORT

The complete 19-page penetration-testing report is available in this repository.

**Document:** `W4-Pentest-Report.pdf`

The final report includes:

- Liability disclaimer
- Introduction
- Executive summary
- Project objectives
- Scope of assessment
- Methodology
- Tools used
- Activities performed
- Security findings
- Risk analysis
- Recommendations
- Evidence and documentation
- Limitations
- Conclusion

<div align="center">

<a href="W4-Pentest-Report.pdf">
<img src="https://img.shields.io/badge/VIEW_FULL_REPORT-00FF88?style=for-the-badge&labelColor=080808" />
</a>

</div>

---

## 🛡️ `09` — RECOMMENDATIONS

The report provides remediation recommendations for the identified findings:

| Finding | Recommended Action |
|:---|:---|
| W4-F04 | Enforce strong, randomly generated PDF passwords and modern encryption standards |
| W4-F01 | Conduct source-code review, implement parameterized queries and review session/authorization logic |
| W4-F05 | Review access controls on internal organizational data and conduct an internal exposure audit |
| W4-F02 | Configure CSP, HSTS, X-Content-Type-Options and Referrer-Policy |
| W4-F03 | Decommission or properly access-restrict the legacy `/old/` interface |

---

## 🎯 `10` — SKILLS DEMONSTRATED

```text
[+] Reconnaissance and Footprinting
[+] WHOIS and DNS Enumeration
[+] Website Technology Fingerprinting
[+] Network and Service Identification
[+] HTTP Response Analysis
[+] Web Application Investigation
[+] Authentication Security Testing
[+] SQL Injection-Related Testing
[+] PDF Hash Extraction
[+] Password Recovery and Verification
[+] Information Exposure Investigation
[+] Risk Assessment
[+] Technical Documentation and Reporting
```

---

## ⚖️ `11` — DISCLAIMER

This project was conducted as part of the NetworkWalks Cybersecurity Program for educational and training purposes.

The assessment was conducted with written authorization secured directly from Mediroza General Hospital and within the approved testing scope.

All patient, staff and shareholder data referenced in the assessment was fictional lab data constructed for training purposes. The findings reflect the observations and evidence collected during the assessment and do not represent an actual data breach.

The assessment was subject to limitations, including the absence of source-code access, restricted testing scope, and exclusion of destructive testing, denial-of-service techniques, brute-force attacks and rate-limit-bypass methods.

This repository is intended for educational and professional portfolio demonstration.

---

## 👨‍💻 `12` — AUTHOR

<div align="center">

### MUHAMMED IRFAN

**Cybersecurity Professional | NetworkWalks – Batch B084**

Network Security • Vulnerability Assessment • Penetration Testing • Security Operations

[LinkedIn Profile](https://www.linkedin.com/in/muhd-irfan-03500250x)

</div>

---

<div align="center">

### ⚡ NETWORKWALKS — WEEK 04

**LEARN • ANALYZE • TEST • SECURE**

*Building practical cybersecurity skills through hands-on security assessments.*

</div>
