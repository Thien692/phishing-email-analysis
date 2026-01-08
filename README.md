# phishing-email-analysis
SOC-style phishing email analysis including header inspection, SPF validation, URL defanging, VirusTotal intelligence, and incident reporting.

## Phishing Email Analysis (SOC Project)

### Overview

This project demonstrates a **SOC-style phishing email investigation** following real-world blue team workflows.
The goal is to analyze a suspicious email, identify malicious indicators, and produce a professional **incident response report**.

---

## Objectives

* Analyze email headers to identify sender infrastructure
* Validate email authentication (SPF)
* Investigate sender IP ownership
* Extract and defang suspicious URLs
* Perform threat intelligence analysis using VirusTotal
* Determine whether the email is legitimate or malicious
* Produce a SOC-style incident report

---

## Tools & Techniques

* Email header analysis
* SPF validation
* Whois IP lookup
* DNS resolution (nslookup)
* URL defanging
* VirusTotal threat intelligence
* Fortinet reputation analysis

---

## 📩 Email Analysis Summary

| Field         | Value                                                                               |
| ------------- | ----------------------------------------------------------------------------------- |
| Delivery Date | Tue, 31 Oct 2023 10:10:04 -0900                                                     |
| Subject       | Your account has been flagged for unusual activity                                  |
| Recipient     | [dderringer@mighty-solutions.net](mailto:dderringer@mighty-solutions.net)           |
| Display Name  | Outlook Support Team                                                                |
| Sender Email  | [social201511138@social.helwan.edu.eg](mailto:social201511138@social.helwan.edu.eg) |
| Return-Path   | [social201511138@social.helwan.edu.eg](mailto:social201511138@social.helwan.edu.eg) |
| Sender IP     | 40.107.22.60                                                                        |
| Hostname      | mail-am6eur05on2060.outbound.protection.outlook.com                                 |
| IP Owner      | Microsoft Corporation                                                               |
| SPF Result    | Pass                                                                                |
| SPF Record    | v=spf1 include:spf.protection.outlook.com -all                                      |
| Message-ID    | JMrByPl2c3HBo8SctKnJ5C5Gp64sPSSWk76p4sjQ@s6                                         |
| Encoding      | base64                                                                              |

---

##  URL Analysis

**Suspicious URL (Defanged):**

```
hxxps[://]0[.]232[.]205[.]92[.]host[.]secureserver[.]net/lclbluewin08812/
```

**VirusTotal Verdict (Fortinet):**

```
Phishing
```

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
social201511138@social.helwan.edu.eg
```

---

## Analysis Conclusion

Although the email passed SPF and was sent using Microsoft infrastructure, multiple red flags were identified:

* Brand impersonation (Outlook Support Team)
* Sender domain mismatch
* Obfuscated content (base64 encoding)
* Confirmed phishing URL by VirusTotal (Fortinet)

---

## Final Verdict

**Malicious – Phishing Email**

---

## Recommended SOC Actions

* Block the malicious URL at email gateway and firewall
* Quarantine similar emails
* Reset user credentials if interaction occurred
* Add IOCs to SIEM and threat feeds
* Conduct user awareness training

---

## Skills Demonstrated

* SOC Tier 1 email analysis
* Phishing detection
* Header and infrastructure investigation
* Threat intelligence correlation
* Incident reporting

---

## Disclaimer

This project was conducted in a **controlled lab environment** for educational purposes only.

---

