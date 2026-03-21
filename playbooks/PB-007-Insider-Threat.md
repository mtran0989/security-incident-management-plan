# PB-007 — Insider Threat
## Incident Response Playbook | NexaCore Technologies

| Attribute | Detail |
|---|---|
| **Playbook ID** | PB-007 |
| **Incident Category** | Insider Threat |
| **Default Severity** | See classification table below |
| **Last Review** | April 2026 |
| **Owner** | Lead Incident Analyst |

---

## 1. Incident Description

Insider threats involve current or former employees, contractors, or privileged users who misuse their authorized access — either maliciously (data theft, sabotage) or negligently (accidental data exposure, policy violation). Insider threats are among the most difficult to detect and are treated with particular care regarding evidence preservation and Legal/HR coordination.

---

## 2. Trigger Conditions

-e - UEBA alert: unusual data access volumes or off-hours activity for specific user
- DLP alert: employee uploading large volumes of data to personal cloud storage
- HR notification of employee resignation with access to sensitive data
- Manager report of suspicious employee behavior or access
- IT ticket: terminated employee account showing activity after offboarding

---

## 3. Severity Classification

| Condition | Severity |
|---|---|
-e Malicious data theft with Tier 1 data | Critical (T1)
Data theft without Tier 1 data | High (T2)
Policy violation, no confirmed malicious intent | Medium (T3)

---

## 4. Immediate Actions (First 30 Minutes)

- [ ] Analyst: Acknowledge alert; open incident ticket in ServiceNow
- [ ] Analyst: Notify Incident Commander
- [ ] IC: Assess severity and activate appropriate CIRT members
- [ ] IC: Notify CISO if Tier 1 or Tier 2
- [ ] Analyst: Begin preservation of relevant logs and evidence
- [ ] Analyst: Complete initial scope assessment

---

## 5. Containment Actions

-e - **CRITICAL: Do NOT confront the suspect or take action that alerts them before Legal/HR authorize it**
- Coordinate all containment actions with HR and Legal before execution
- Preserve all evidence before revoking access
- Work with Legal to determine if law enforcement notification is appropriate
- Once authorized: revoke access, preserve email and file activity logs, preserve system images

---

## 6. Eradication

- [ ] Identify and remove root cause of the incident
- [ ] Patch or mitigate the exploited vulnerability or misconfiguration
- [ ] Rotate all credentials or keys involved in the incident
- [ ] Validate eradication with post-remediation scan or audit

---

## 7. Recovery

- [ ] Restore affected services to normal operations
- [ ] Validate functionality and security posture before returning to production
- [ ] Apply enhanced monitoring for 14–30 days post-incident
- [ ] Brief affected teams and document recovery actions

---

## 8. Evidence Collection

- [ ] Alert data and supporting logs from detection source
- [ ] Authentication logs for accounts involved
- [ ] Network traffic logs for the incident window
- [ ] System logs from affected assets
- [ ] Cloud audit logs (Azure Activity Log, Azure AD) if applicable

---

## 9. Post-Incident Requirements

- [ ] Complete post-incident review within 5 business days (T1/T2) or 10 business days (T3)
- [ ] Produce formal incident report for T1/T2
- [ ] Document lessons learned and assign remediation action items
- [ ] Update detection rules based on incident IOCs and TTPs

---

*PB-007 v1.0 — NexaCore Technologies — April 2026*
