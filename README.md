# Phishing & Account Takeover Investigation (SIEM Analysis)

## 📌 Project Overview
This repository contains a comprehensive incident response investigation based on SIEM, Firewall, and Email security logs. The case tracks a coordinated **Spear-Phishing Campaign** targeting multiple corporate endpoints (`thetrydaily.thm`), which resulted in a successful **Account Takeover (ATO)** and subsequent internal anomalous activity. 

This project demonstrates practical skills in:
- Multi-source log correlation (Email Gateway, Perimetric Firewall, and SIEM indexes).
- Timeline construction and forensic analysis.
- Threat Hunting and identification of Indicators of Compromise (IOCs).
- Remediation and Containment planning following the **NIST SP 800-61** framework.

---

## 📊 Incident Timeline & Event Correlation

By analyzing the timestamp logs from the event collector (`host = 10.10.161.89:8989`), the attack sequence was reconstructed chronologically:

```
 - Initial Inbound Phishing email arrives at j.garcia@thetrydaily.thm (HR-Theme)
      
 - User (j.garcia) sends a legitimate internal email (Confirms active session)
      
 - Endpoint 10.20.2.17 (j.garcia) triggers HIGH alert: Firewall blocks malicious short URL (bit.ly)
      
 - Second Inbound Phishing email hits c.allen@thetrydaily.thm (IT/Microsoft Typosquatting Theme)
      
 - Account Takeover Confirmed: j.garcia's account starts automated internal spamming to itself
```
