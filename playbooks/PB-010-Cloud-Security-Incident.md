# PB-010 — Cloud Security Incident (Azure)
## Incident Response Playbook | NexaCore Technologies

| Attribute | Detail |
|---|---|
| **Playbook ID** | PB-010 |
| **Incident Category** | Cloud Security Incident (Azure) |
| **Default Severity** | See classification table below |
| **Last Review** | April 2026 |
| **Owner** | Lead Incident Analyst |

---

## 1. Incident Description

Cloud security incidents include misconfiguration exposing data publicly, unauthorized access to Azure resources, abuse of cloud service accounts, or exploitation of cloud management plane vulnerabilities. NexaCore's primary cloud environment is Microsoft Azure.

---

## 2. Trigger Conditions

-e - Microsoft Defender for Cloud alert: publicly accessible storage account, over-permissioned role assignment
- Azure AD alert: suspicious service principal activity or new credential added to application
- Azure Sentinel: anomalous Azure Resource Manager operations
- Security researcher reports publicly accessible NexaCore Azure storage blob
- Azure Activity Log: unexpected subscription-level changes or role assignments

---

## 3. Severity Classification

| Condition | Severity |
|---|---|
-e Public exposure of Tier 1 data in Azure storage | Critical (T1)
Azure service principal compromise with privileged roles | Critical (T1)
Misconfiguration with no confirmed data access | High (T2)

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

-e - Revoke the misconfigured access immediately (remove public access, revoke over-permissioned role)
- Disable the compromised service principal or managed identity
- Apply Azure Policy to prevent recurrence of the misconfiguration
- Preserve Azure Activity Logs and Azure AD audit logs for the incident window
- Review all resources created or modified by the compromised identity

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

*PB-010 v1.0 — NexaCore Technologies — April 2026*
