# PB-006 — Supply Chain & Third-Party Compromise
## Incident Response Playbook | NexaCore Technologies

| Attribute | Detail |
|---|---|
| **Playbook ID** | PB-006 |
| **Incident Category** | Supply Chain & Third-Party Compromise |
| **Default Severity** | See classification table below |
| **Last Review** | April 2026 |
| **Owner** | Lead Incident Analyst |

---

## 1. Incident Description

A supply chain incident occurs when an attacker compromises a vendor, software provider, or third-party integration to gain access to NexaCore systems. These incidents are particularly dangerous because the attack originates from a trusted source. Notable examples: SolarWinds, 3CX, MOVEit.

---

## 2. Trigger Conditions

-e - Vendor or software provider notifies NexaCore of a security incident
- CISA advisory for a vendor product NexaCore uses
- Anomalous activity from a known-trusted IP range (vendor network)
- Unexpected API calls from vendor service accounts
- Software update from trusted vendor contains malicious code

---

## 3. Severity Classification

| Condition | Severity |
|---|---|
-e Vendor with Tier 1 system access compromised | Critical (T1)
Vendor with Tier 2 system access compromised | High (T2)
Vendor with read-only access to Internal data | Medium (T3)

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

-e - Immediately revoke API keys, access tokens, and service account credentials for the affected vendor
- Disable vendor integrations and API endpoints
- Block vendor IP ranges until investigation is complete
- Preserve all logs of vendor activity for the prior 90 days
- Notify Legal: third-party incidents may trigger contractual notification obligations

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

*PB-006 v1.0 — NexaCore Technologies — April 2026*
