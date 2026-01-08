# phishing-email-analysis

SOC-style phishing email analysis focusing on header inspection, SPF validation, URL defanging, threat intelligence correlation using VirusTotal, and incident reporting.

---

## Phishing Email Analysis (SOC Project)

## Overview

This project demonstrates a SOC-style phishing email investigation aligned with real-world blue team workflows.  
The objective is to analyze a suspicious email, identify malicious indicators, and produce a professional incident response report.

---

## Objectives

- Analyze email headers to identify sender infrastructure
- Validate email authentication mechanisms (SPF)
- Investigate sender IP ownership and hosting infrastructure
- Extract and defang suspicious URLs
- Perform threat intelligence analysis using VirusTotal
- Determine whether the email is legitimate or malicious
- Produce a SOC-style incident response report

---

## Tools & Techniques

- Email header analysis
- SPF validation
- Whois IP lookup
- DNS resolution (nslookup)
- URL defanging
- VirusTotal threat intelligence
- Vendor reputation analysis (Fortinet)

---

## Email Analysis Summary

| Field | Value |
|------|------|
| Delivery Date | Tue, 31 Oct 2023 10:10:04 -0900 |
| Subject | Your account has been flagged for unusual activity |
| Recipient | dderringer@mighty-solutions.net |
| Display Name | Outlook Support Team |
| Sender Email | social201511138@social.helwan.edu.eg |
| Return-Path | social201511138@social.helwan.edu.eg |
| Sender IP | 40.107.22.60 |
| Hostname | mail-am6eur05on2060.outbound.protection.outlook.com |
| IP Owner | Microsoft Corporation |
| SPF Result | Pass |
| SPF Record | v=spf1 include:spf.protection.outlook.com -all |
| Message-ID | JMrByPl2c3HBo8SctKnJ5C5Gp64sPSSWk76p4sjQ@s6 |
| Encoding | base64 |

---

## URL Analysis

**Suspicious URL (Defanged):**
```

hxxps[://]0[.]232[.]205[.]92[.]host[.]secureserver[.]net/lclbluewin08812/

```
---

## Supporting Evidence & Investigation Details

Detailed supporting evidence, command output, and threat intelligence screenshots related to this phishing investigation are documented in the following GitHub issue:

<details>
  <summary><strong>Phishing URL Investigation – Evidence & Findings</strong></summary>

  This issue includes:
  - Extracted email header artifacts
  - Defanged and refanged malicious URLs
  - VirusTotal analysis results
  - Vendor detection breakdown
  - Screenshot evidence supporting phishing classification

  🔗 https://github.com/Thien692/phishing-email-analysis/issues/1

</details>


### VirusTotal Analysis

The extracted URL was analyzed using VirusTotal to assess its reputation.

**Detection Summary:**
- 6 out of 98 security vendors flagged the URL as malicious
- Reputable vendors classifying the URL as phishing include:
  - Fortinet
  - ESET
  - Kaspersky
  - Sophos
  - CyRadar
  - Phishing Database

**Assessment:**
Although the overall detection ratio is relatively low, detections from multiple well-established security vendors indicate a high-confidence phishing classification.

---

## Indicators of Compromise (IOCs)

**Malicious URL**
```

hxxps[://]0[.]232[.]205[.]92[.]host[.]secureserver[.]net/lclbluewin08812/

```

**Sender IP**
```

40.107.22.60

```

**Sender Email**
```

[social201511138@social.helwan.edu.eg](mailto:social201511138@social.helwan.edu.eg)

```

---

## Analysis Conclusion

Although the email passed SPF validation and was delivered through Microsoft-owned infrastructure, several indicators strongly suggest malicious intent:

- Brand impersonation of a trusted service (Outlook Support Team)
- Sender domain mismatch inconsistent with the claimed sender identity
- Obfuscated email content using base64 encoding
- Threat intelligence confirmation of a phishing URL via VirusTotal

---

## Final Verdict

**Malicious – Phishing Email**

---

## Recommended SOC Actions

- Block the malicious URL at the email gateway and perimeter firewall
- Quarantine similar emails across the organization
- Reset affected user credentials if interaction occurred
- Add identified IOCs to SIEM and threat intelligence feeds
- Conduct user awareness training to reduce future phishing risk

---

## Skills Demonstrated

- SOC Tier 1 email investigation
- Phishing detection and analysis
- Email header and infrastructure analysis
- Threat intelligence correlation
- Incident response reporting

---

## Disclaimer

This project was conducted in a controlled lab environment for educational and demonstration purposes only.

