# NIST SP 800-61 Rev. 3 — Framework Summary
## NexaCore Technologies | Reference Document

| Attribute | Detail |
|---|---|
| **Document** | NIST Special Publication 800-61 Revision 3 |
| **Title** | Incident Response Recommendations and Considerations for Cybersecurity Risk Management: A CSF 2.0 Community Profile |
| **Published** | April 3, 2025 |
| **Supersedes** | NIST SP 800-61 Rev. 2 (August 2012) |
| **URL** | https://csrc.nist.gov/pubs/sp/800/61/r3/final |
| **NexaCore Adoption** | Primary IR governance framework |

---

## Key Changes from Rev. 2 to Rev. 3

### 1. CSF 2.0 Integration
Rev. 3 fully aligns incident response to the six functions of NIST CSF 2.0: **Govern, Identify, Protect, Detect, Respond, and Recover**. The previous four-phase lifecycle (Preparation, Detection/Analysis, Containment/Eradication/Recovery, Post-Incident) is replaced with this function-based model.

### 2. New Incident Response Lifecycle Model
Rev. 3 introduces a new lifecycle model that recognizes the continuous, dynamic nature of modern incidents. Unlike the circular lifecycle in Rev. 2 that treated incidents as discrete events, Rev. 3 acknowledges that:
- Incidents are increasingly complex and may involve multiple attack surfaces simultaneously
- Detection, response, and recovery often occur in parallel rather than sequentially
- Incident response activities are continuous organizational capabilities, not periodic reactions

### 3. Living Resource Model
Due to the rapid pace of change in incident response best practices, Rev. 3 moves specific technical guidance to a continuously updated NIST Incident Response website (https://www.nist.gov/incident-response) rather than including it in the static publication.

### 4. Expanded Governance Emphasis
The Govern function is new in CSF 2.0 and plays a significant role in Rev. 3, emphasizing that incident response must be integrated into organizational risk management, not treated as a standalone security function.

---

## CSF 2.0 Functions and Incident Response Roles

### GOVERN (GV)
**Role:** Establishes the organizational context for all incident response activities.

**Key IR Activities:**
- Develop and maintain incident response policy
- Define roles, responsibilities, and decision authority
- Integrate IR into enterprise risk management
- Establish performance metrics and reporting cadence
- Ensure legal, regulatory, and contractual obligations are understood

**NexaCore Implementation:** Incident Response Policy (POL-SEC-IR-001), IRP governance section, CIRT charter

---

### IDENTIFY (ID)
**Role:** Provides the intelligence base that enables effective incident prioritization.

**Key IR Activities:**
- Maintain current asset inventory with criticality ratings
- Conduct risk assessments to prioritize IR resource allocation
- Identify threat types most relevant to the organization
- Map data assets to regulatory obligations
- Establish external threat intelligence sources

**NexaCore Implementation:** Asset criticality tiers (T1/T2/T3), data classification schema, FS-ISAC membership, Tenable vulnerability scanning

---

### PROTECT (PR)
**Role:** Reduces incident likelihood and limits scope when incidents do occur.

**Key IR Activities:**
- Implement access controls to limit blast radius
- Deploy endpoint protection to reduce malware execution
- Train personnel to recognize and report incidents
- Implement data loss prevention controls
- Segment networks to limit lateral movement

**NexaCore Implementation:** Azure AD + PIM, MFA enforcement, Defender for Endpoint, DLP policies, network segmentation

---

### DETECT (DE)
**Role:** Surface indicators of compromise as quickly as possible to minimize dwell time.

**Key IR Activities:**
- Deploy SIEM with comprehensive log collection and detection rules
- Implement EDR on all endpoints
- Configure UEBA for anomaly detection
- Subscribe to threat intelligence feeds for IOC-based detection
- Establish monitoring for cloud environments

**NexaCore Implementation:** Microsoft Sentinel, Defender for Endpoint, Azure Defender for Cloud, FS-ISAC threat feeds

---

### RESPOND (RS)
**Role:** Contain and eradicate threats once detected.

**Key IR Activities:**
- Execute containment procedures per playbooks
- Preserve forensic evidence
- Communicate with stakeholders per communication plan
- Coordinate with external parties (law enforcement, regulators, insurance)
- Document all response activities

**NexaCore Implementation:** CIRT + playbooks, ServiceNow tracking, communication templates, external retainer

---

### RECOVER (RC)
**Role:** Restore systems and services to normal operations.

**Key IR Activities:**
- Restore from clean backups or rebuild systems
- Validate system integrity before returning to production
- Apply enhanced monitoring during recovery period
- Communicate recovery status to stakeholders
- Incorporate lessons learned into prevention controls

**NexaCore Implementation:** Azure Backup + Site Recovery, recovery validation checklists, post-recovery monitoring uplift

---

## NexaCore IRP Alignment Matrix

| NIST SP 800-61 Rev. 3 Guidance | NexaCore IRP Section | Document Reference |
|---|---|---|
| Incident response policy and plan | Section 4.1–4.2 | POL-SEC-IR-001 |
| CSIRT establishment | Section: CIRT Structure | IRP Phase 1 |
| Asset inventory | Section: Phase 1.4 | CMDB + Tenable |
| Detection capabilities | Section: Phase 2.1 | Sentinel, Defender |
| Incident declaration process | Section: Phase 2.3 | Incident Declaration Form |
| Containment procedures | Section: Phase 3 | Playbooks PB-001 through PB-010 |
| Evidence preservation | Section: Evidence Handling | Evidence CoC Log |
| Communication procedures | Section: Communication | Communication matrix |
| Post-incident activity | Section: Phase 6 | Post-Incident Review Agenda |
| Metrics and improvement | Section: Metrics & KPIs | ServiceNow dashboards |

---

## Additional NIST Resources Referenced

| Publication | Title | NexaCore Application |
|---|---|---|
| NIST SP 800-53 Rev. 5 | Security and Privacy Controls | IR-1 through IR-10 control family compliance |
| NIST SP 800-86 | Guide to Integrating Forensic Techniques | Evidence handling procedures |
| NIST SP 800-92 | Guide to Computer Security Log Management | Log retention and SIEM configuration |
| NIST SP 800-137 | Information Security Continuous Monitoring | Continuous monitoring program |
| NIST CSF 2.0 | Cybersecurity Framework | Governance and risk management structure |

---

*NexaCore Technologies — NIST SP 800-61r3 Reference Summary v1.0 — April 2026*
