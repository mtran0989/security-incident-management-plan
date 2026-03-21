# Incident Declaration Form
## NexaCore Technologies — Computer Incident Response Team

> **Complete this form immediately upon declaring a security incident. This is the official record of incident declaration and serves as the starting point of the incident timeline. All fields must be completed within 30 minutes of declaration for Tier 1/2 incidents.**

---

## Section 1 — Declaration Details

| Field | Response |
|---|---|
| **Incident ID** | INC-[YYYY]-[NNNN] (assigned by ServiceNow) |
| **Declaration Timestamp (UTC)** | |
| **Declared By** | Name / Title |
| **Incident Commander Assigned** | |
| **ServiceNow Ticket #** | |

---

## Section 2 — Incident Classification

**Severity Tier** (circle one): &nbsp; **CRITICAL (T1)** &nbsp;|&nbsp; **HIGH (T2)** &nbsp;|&nbsp; **MEDIUM (T3)** &nbsp;|&nbsp; **LOW (T4)**

**Incident Category** (check all that apply):

- [ ] Ransomware / Destructive Malware
- [ ] Data Breach / Unauthorized Exfiltration
- [ ] Business Email Compromise / Financial Fraud
- [ ] Credential Compromise / Account Takeover
- [ ] Denial of Service (DoS/DDoS)
- [ ] Supply Chain / Third-Party Compromise
- [ ] Insider Threat
- [ ] Phishing / Spear-Phishing Campaign
- [ ] Vulnerability Exploitation (Active)
- [ ] Cloud Security Incident
- [ ] Other: ___________________________

**Applicable Playbook(s):** PB-_____

---

## Section 3 — Detection Details

| Field | Response |
|---|---|
| **Detection Timestamp (UTC)** | |
| **Detection Source** | (SIEM / EDR / Employee Report / Third Party / Other) |
| **Alert ID / Rule Name** | |
| **Initial Alert Description** | |

---

## Section 4 — Initial Scope Assessment

**Systems confirmed or suspected affected:**

| System / Hostname | Role / Tier | Confirmed or Suspected | Actions Taken |
|---|---|---|---|
| | | | |
| | | | |
| | | | |

**Data potentially involved:**

- [ ] Cardholder Data (CHD) — PCI in scope
- [ ] Customer PII
- [ ] Employee PII
- [ ] Internal / Confidential business data
- [ ] No sensitive data confirmed — investigation ongoing
- [ ] Unknown at time of declaration

**Estimated number of records potentially affected:** _______________

**Is the threat actor currently active in the environment?**
- [ ] Yes — confirmed active
- [ ] Possibly — under investigation
- [ ] No — historical activity only
- [ ] Unknown

**Is data exfiltration confirmed or suspected?**
- [ ] Confirmed
- [ ] Suspected
- [ ] Not suspected
- [ ] Unknown

---

## Section 5 — Initial Vector Assessment

**Suspected initial access vector:**

- [ ] Phishing / Spear-phishing
- [ ] Credential stuffing / Password spray
- [ ] Vulnerability exploitation (specify CVE if known): _______________
- [ ] Supply chain / Vendor compromise
- [ ] Insider action
- [ ] Unknown — under investigation
- [ ] Other: _______________

---

## Section 6 — Regulatory Impact Assessment

**Does this incident trigger regulatory notification obligations?**

| Regulation | Triggered? | Notification Deadline | Legal Counsel Notified? |
|---|---|---|---|
| PCI DSS (CHD involved) | Yes / No / Unknown | Immediately | Yes / No |
| GLBA (customer financial data) | Yes / No / Unknown | 30 days | Yes / No |
| State Breach Law (PII involved) | Yes / No / Unknown | Varies by state | Yes / No |
| Contractual client notification | Yes / No / Unknown | Per contract | Yes / No |

**Legal Counsel Notified:** Yes / No | Timestamp: _____________ | Name: _________________

---

## Section 7 — CIRT Activation

| Role | Name | Notified (Y/N) | Notification Time (UTC) | Contact Method |
|---|---|---|---|---|
| Incident Commander | | | | |
| CISO | | | | |
| Lead Incident Analyst | | | | |
| Forensic Investigator | | | | |
| Threat Intelligence Lead | | | | |
| IT Infrastructure Lead | | | | |
| Legal Counsel | | | | |
| CCO (if T1/T2) | | | | |

---

## Section 8 — Initial Containment Actions Taken

| Timestamp (UTC) | Action | Analyst | System / Account Affected |
|---|---|---|---|
| | | | |
| | | | |
| | | | |

---

## Section 9 — Secure Communications

**Incident Teams Channel:** `INC-[YYYY]-[NNNN]-[Category]`

**Out-of-band channel activated?** Yes / No

**Reason for out-of-band (if yes):** _______________________________________________

---

## Section 10 — Declarant Signature

By completing this form, I confirm that a security incident has been declared in accordance with NexaCore's Incident Response Policy and that this record accurately reflects the known facts at time of declaration.

**Name:** _________________________________

**Title:** _________________________________

**Signature:** _________________________________

**Date/Time (UTC):** _________________________________

---

*NexaCore Technologies — Incident Declaration Form v1.0 — April 2026*
*This document is CONFIDENTIAL. Distribute only on a need-to-know basis.*
