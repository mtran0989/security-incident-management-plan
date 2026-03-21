# PB-008 — Phishing & Spear-Phishing Campaign
## Incident Response Playbook | NexaCore Technologies

| Attribute | Detail |
|---|---|
| **Playbook ID** | PB-008 |
| **Incident Category** | Phishing & Spear-Phishing Campaign |
| **Default Severity** | See classification table below |
| **Last Review** | April 2026 |
| **Owner** | Lead Incident Analyst |

---

## 1. Incident Description

Phishing is the most common initial access vector in enterprise breaches. NexaCore is a high-value target for spear-phishing given its role in payment processing. This playbook covers phishing campaigns targeting employees, with or without successful credential compromise.

---

## 2. Trigger Conditions

-e - Employee reports suspicious email requesting credentials or containing unusual attachment
- Defender for O365 alert: malicious URL or attachment detected
- Multiple employees report the same suspicious email (campaign indicator)
- Credential harvest page impersonating NexaCore or Microsoft 365 detected
- Successful login from credential harvesting page detected in Azure AD logs

---

## 3. Severity Classification

| Condition | Severity |
|---|---|
-e Confirmed credential compromise from phishing | High (T2)
Phishing with malicious attachment opened | High (T2)
Phishing email received but no interaction | Low (T4)

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

-e - Remove the phishing email from all mailboxes immediately (Defender for O365: soft delete)
- Block the sender domain and all URLs in the email at the email gateway
- If credentials were entered: immediately treat as credential compromise (see PB-004)
- Notify all employees who received the email via out-of-band communication
- Block the phishing page domain at Palo Alto firewall

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

*PB-008 v1.0 — NexaCore Technologies — April 2026*
