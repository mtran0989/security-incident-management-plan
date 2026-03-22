# Incident Report
## NexaCore Technologies — Computer Incident Response Team

> **Classification: CONFIDENTIAL — Attorney-Client Privileged**
> *This report is prepared at the direction of Legal Counsel and may be protected by attorney-client and work-product privileges. Distribution is restricted.*

---

## Report Header

| Field | Detail |
|---|---|
| **Incident ID** | INC-[YYYY]-[NNNN] |
| **Report Version** | [1.0 — Initial / 2.0 — Final] |
| **Report Date** | |
| **Prepared By** | Lead Incident Analyst / IR Program Manager |
| **Reviewed By** | Incident Commander, CISO, Legal Counsel |
| **Distribution** | CISO, General Counsel, CEO [add as appropriate for severity] |
| **Incident Severity** | Tier [1/2/3] — [Critical/High/Medium] |
| **Incident Category** | |
| **Incident Status** | [Open / Contained / Closed] |

---

## Part I — Executive Summary

*[Non-technical summary suitable for executive and board audience. 1–2 paragraphs maximum. Cover: what happened, when it was detected, what was affected, what actions were taken, and current status. Avoid technical jargon.]*

**Example:**
> On [DATE], NexaCore's Security Operations Center detected [INCIDENT DESCRIPTION]. The incident affected [X systems / X records]. The Incident Response Team activated at [TIME] and [CONTAINMENT ACTION] was completed by [TIME]. [DATA TYPE / NO DATA] was confirmed to have been [ACCESSED / EXFILTRATED / NOT ACCESSED]. All affected systems were restored to normal operations by [DATE]. This report documents the full incident timeline, root cause, and remediation actions taken.

**Business Impact Summary:**

| Impact Category | Assessment |
|---|---|
| Financial Impact | [Estimated / None identified / Under assessment] |
| Operational Impact | [Duration of disruption, systems affected] |
| Reputational Impact | [Customer notification required / No external disclosure] |
| Regulatory Impact | [Notifications triggered / None required] |
| Data Impact | [Records affected, data classification] |

---

## Part II — Incident Timeline

*[Chronological reconstruction of all confirmed events. UTC timestamps required. Include both attacker activity and CIRT response actions.]*

| Timestamp (UTC) | Event | Source | Analyst |
|---|---|---|---|
| | **[INITIAL COMPROMISE / FIRST ATTACKER ACTION]** | | |
| | | | |
| | **[DETECTION — First indicator observed]** | | |
| | | | |
| | **[INCIDENT DECLARED]** | | |
| | **[CIRT ACTIVATED]** | | |
| | | | |
| | **[CONTAINMENT ACHIEVED]** | | |
| | | | |
| | **[ERADICATION COMPLETE]** | | |
| | | | |
| | **[RECOVERY COMPLETE / SYSTEMS RESTORED]** | | |
| | | | |
| | **[INCIDENT CLOSED]** | | |

**Key Time Intervals:**

| Metric | Value |
|---|---|
| Time from initial compromise to detection (MTTD) | |
| Time from detection to incident declaration | |
| Time from declaration to containment (MTTC) | |
| Time from containment to full recovery (MTTR) | |

---

## Part III — Technical Analysis

### 3.1 Initial Access Vector

*[How the attacker gained initial access. Be specific: vulnerability exploited (CVE), phishing lure details, credential source, etc.]*

### 3.2 Attack Chain (Kill Chain / MITRE ATT&CK Mapping)

#### ATT&CK Kill Chain
| Phase | Tactic | Technique ID | Description | Evidence Source |
|---|---|---|---|---|
| 1 | Initial Access | | | |
| 2 | Execution | | | |
| 3 | Persistence | | | |


| Phase | MITRE ATT&CK Technique | Description | Evidence Source |
|---|---|---|---|
| Initial Access | | | |
| Execution | | | |
| Persistence | | | |
| Privilege Escalation | | | |
| Defense Evasion | | | |
| Credential Access | | | |
| Discovery | | | |
| Lateral Movement | | | |
| Collection | | | |
| Exfiltration | | | |
| Impact | | | |

### 3.3 Systems Affected

| System | Tier | Compromise Confirmed | Actions Taken | Restored |
|---|---|---|---|---|
| | | | | |

### 3.4 Data Impact Assessment

| Data Category | Volume Accessed | Volume Exfiltrated | Data Owner Notified |
|---|---|---|---|
| Cardholder Data (CHD) | | | |
| Customer PII | | | |
| Employee PII | | | |
| Internal / Confidential | | | |

### 3.5 Indicators of Compromise (IOCs)

| IOC Type | Value | Confidence | Disposition |
|---|---|---|---|
| IP Address | | High/Med/Low | Blocked / Monitoring |
| Domain | | | |
| File Hash (SHA-256) | | | |
| Email Address | | | |
| URL | | | |

---

## Part IV — Root Cause Analysis

### 4.1 Root Cause

*[The definitive determination of why the incident occurred. Identify the specific vulnerability, misconfiguration, or control gap that enabled the incident.]*

**Primary Root Cause:**

**Contributing Factors:**
1.
2.
3.

### 4.2 Detection Gap Analysis

| Question | Finding |
|---|---|
| Was the incident detected by existing monitoring? | Yes / No |
| If no: what detection capability was missing? | |
| How long did the incident go undetected? | |
| What detection would have caught this earlier? | |

### 4.3 Control Gap Analysis

| Control Gap | Description | Risk |
|---|---|---|
| | | |

---

## Part V — Actions Taken During Response

*[Summary of all significant response actions. Full detail is in the incident ticket timeline.]*

### Containment Actions

| Action | Timestamp | Analyst | Outcome |
|---|---|---|---|
| | | | |

### Eradication Actions

| Action | Timestamp | Analyst | Validation |
|---|---|---|---|
| | | | |

### Recovery Actions

| System / Service | Restoration Method | Validation | Restored By |
|---|---|---|---|
| | | | |

---

## Part VI — Regulatory & Notification Actions

| Obligation | Required? | Action Taken | Date | Owner |
|---|---|---|---|---|
| PCI DSS notification | | | | |
| GLBA notification | | | | |
| State breach notification | | | | |
| Customer notification | | | | |
| Law enforcement | | | | |
| Cyber insurance | | | | |

---

## Part VII — Recommendations

### 7.1 Immediate Remediation Items (Complete within 30 days)

| # | Recommendation | Owner | Due Date | Priority |
|---|---|---|---|---|
| 1 | | | | Critical |
| 2 | | | | High |

### 7.2 Strategic Improvements (Complete within 90 days)

| # | Recommendation | Owner | Due Date |
|---|---|---|---|
| 1 | | | |

### 7.3 Program Improvements

| Area | Current Gap | Recommended Improvement |
|---|---|---|
| Detection | | |
| Response procedures | | |
| Training | | |
| Tooling | | |

---

## Part VIII — Evidence Inventory

| Evidence ID | Type | Description | Hash (SHA-256) | Collected By | Location |
|---|---|---|---|---|---|
| EV-001 | | | | | |

---

*NexaCore Technologies — Incident Report Template v1.0 — April 2026*
*CONFIDENTIAL — Attorney-Client Privileged*
