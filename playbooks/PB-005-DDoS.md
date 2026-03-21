# PB-005 — Denial of Service (DoS/DDoS)
## Incident Response Playbook | NexaCore Technologies

| Attribute | Detail |
|---|---|
| **Playbook ID** | PB-005 |
| **Incident Category** | Denial of Service (DoS/DDoS) |
| **Default Severity** | See classification table below |
| **Last Review** | April 2026 |
| **Owner** | Lead Incident Analyst |

---

## 1. Incident Description

A DDoS attack attempts to overwhelm NexaCore's infrastructure, making payment processing services unavailable to clients. Given NexaCore processes 14M daily transactions, availability attacks represent direct revenue impact and potential SLA violations.

---

## 2. Trigger Conditions

-e - Azure DDoS Protection Standard alert
- Significant drop in API response rates or throughput
- Network Operations alert: abnormal inbound traffic volume
- Client reports: inability to reach NexaCore payment APIs
- Palo Alto alert: volumetric traffic anomaly

---

## 3. Severity Classification

| Condition | Severity |
|---|---|
-e Volumetric attack affecting payment processing APIs | Critical (T1)
Attack affecting non-critical endpoints only | High (T2)
Small-scale attack fully mitigated by Azure DDoS | Medium (T3)

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

-e - Activate Azure DDoS Protection Standard (if not already active)
- Enable traffic scrubbing via upstream CDN/scrubbing service
- Implement rate limiting on public-facing APIs via Azure API Management
- Block attacker source IPs/ranges at Palo Alto perimeter
- Coordinate with ISP for upstream filtering if volumetric attack exceeds Azure mitigation capacity
- Activate geo-blocking for regions not servicing legitimate clients if appropriate

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

*PB-005 v1.0 — NexaCore Technologies — April 2026*
