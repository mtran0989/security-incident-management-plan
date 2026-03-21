# NIST CSF 2.0 — Incident Response Mapping
## NexaCore Technologies | Reference Document

---

## Overview

This document maps NexaCore's Incident Response Program activities to the NIST Cybersecurity Framework 2.0 Categories and Subcategories. This mapping supports audit readiness and demonstrates program maturity against the CSF 2.0 standard.

---

## Respond Function (RS) — Primary IR Mapping

### RS.MA — Incident Management

| Subcategory | Description | NexaCore Implementation | Evidence |
|---|---|---|---|
| RS.MA-01 | Potential incidents are tracked and documented | ServiceNow Security Operations ticket management | ServiceNow records |
| RS.MA-02 | Incidents are prioritized based on threat context and severity | Incident severity classification tiers (T1–T4) | IR Policy + Declaration Form |
| RS.MA-03 | Incidents are escalated per authority and impact | Escalation matrix and CIRT activation procedures | IRP Phase 2.2 |
| RS.MA-04 | Incidents are responded to per defined procedures | CIRT activation and playbook execution | Playbooks PB-001 through PB-010 |
| RS.MA-05 | Containment decisions are documented | Incident ticket timeline with containment rationale | ServiceNow records |

### RS.AN — Incident Analysis

| Subcategory | Description | NexaCore Implementation |
|---|---|---|
| RS.AN-03 | Analysis is performed to establish what occurred | Root cause analysis in post-incident report |
| RS.AN-06 | Actions taken during response are documented | Real-time ServiceNow ticket documentation |
| RS.AN-07 | Affected parties are notified as required | Communication matrix + notification templates |
| RS.AN-08 | Cyber threat intelligence is used to support analysis | FS-ISAC feeds + Defender Threat Intelligence |

### RS.CO — Incident Response Reporting and Communication

| Subcategory | Description | NexaCore Implementation |
|---|---|---|
| RS.CO-02 | Information about incidents is communicated to appropriate parties | Executive briefing template + escalation procedures |
| RS.CO-03 | Coordination with external parties occurs | FBI, CISA, regulatory contacts, IR retainer |

### RS.MI — Incident Mitigation

| Subcategory | Description | NexaCore Implementation |
|---|---|---|
| RS.MI-01 | Incidents are contained | Containment procedures per playbook phase |
| RS.MI-02 | Incidents are eradicated | Eradication checklists per playbook |

---

## Recover Function (RC) — Recovery IR Mapping

| Subcategory | Description | NexaCore Implementation |
|---|---|---|
| RC.RP-01 | Recovery is executed per plan | Recovery phase procedures in IRP + playbooks |
| RC.RP-02 | Recovery validation occurs | Pre-production validation checklist |
| RC.RP-03 | Affected parties receive updates during recovery | Executive briefing + client communication |
| RC.RP-04 | Recovery activities are communicated | Incident ticket + executive briefings |
| RC.RP-05 | Recovery plan is updated based on lessons learned | Post-incident review → IRP update cycle |
| RC.RP-06 | Capabilities are restored as planned | Restoration sequencing by asset criticality |

---

## Govern Function (GV) — IR Governance Mapping

| Subcategory | Description | NexaCore Implementation |
|---|---|---|
| GV.OC-01 | Organizational context is established | NexaCore company profile, asset inventory, risk assessment |
| GV.PO-01 | Policy is established and maintained | Incident Response Policy (POL-SEC-IR-001) |
| GV.PO-02 | Policy is reviewed and updated | Annual review cycle + post-T1 review trigger |
| GV.RR-01 | Roles and responsibilities are established | CIRT structure + RACI matrix |
| GV.SC-07 | Suppliers and third parties are included | Vendor IR requirements + third-party notification |

---

*NexaCore Technologies — NIST CSF 2.0 IR Mapping v1.0 — April 2026*
