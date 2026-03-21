# Incident Response Policy
## NexaCore Technologies, Inc.

| Attribute | Detail |
|---|---|
| **Document ID** | POL-SEC-IR-001 |
| **Version** | 1.0 |
| **Status** | Approved |
| **Classification** | Internal Confidential |
| **Owner** | Chief Information Security Officer (CISO) |
| **Approved By** | CISO, General Counsel, CEO |
| **Effective Date** | April 1, 2026 |
| **Next Review** | April 1, 2027 |
| **Framework Alignment** | NIST SP 800-61 Rev. 3 · NIST CSF 2.0 · PCI DSS 4.0 Req. 12.10 · GLBA Safeguards Rule |

---

## 1. Purpose

This Incident Response Policy establishes NexaCore Technologies' organizational commitment to detecting, responding to, and recovering from cybersecurity incidents in a structured, consistent, and legally compliant manner. It defines the governance framework, roles and responsibilities, and minimum requirements for all incident response activities across the enterprise.

Effective incident response is a core component of NexaCore's cybersecurity risk management program. Given the organization's role as a payment processing infrastructure provider, the confidentiality, integrity, and availability of information systems are critical business obligations — not merely regulatory requirements.

---

## 2. Scope

This policy applies to:

- All information systems, applications, networks, and data owned, operated, or managed by NexaCore Technologies
- All employees, contractors, consultants, temporary workers, and third-party service providers with access to NexaCore systems or data
- All NexaCore office locations (Austin TX HQ, Chicago IL, Denver CO) and remote work environments
- All cloud-hosted environments (Microsoft Azure), on-premises data center assets, and SaaS applications
- Third-party integrations, vendor-managed systems, and API connections that process, transmit, or store NexaCore data

---

## 3. Definitions

| Term | Definition |
|---|---|
| **Security Event** | Any observable occurrence in an information system that may indicate an attempt to compromise confidentiality, integrity, or availability |
| **Security Incident** | A security event that has been confirmed to violate security policy, threaten business operations, expose protected data, or trigger a regulatory reporting obligation |
| **Incident Response** | The organized approach to addressing and managing the aftermath of a security incident, with the goals of limiting damage and reducing recovery time and cost |
| **CIRT** | Computer Incident Response Team — NexaCore's core team responsible for executing the incident response program |
| **IOC** | Indicator of Compromise — forensic artifacts that indicate a system may have been compromised |
| **TTPs** | Tactics, Techniques, and Procedures — the behavior patterns used by threat actors |
| **Cardholder Data (CHD)** | Any information printed, processed, transmitted, or stored on a payment card |
| **PII** | Personally Identifiable Information — any data that could identify a specific individual |
| **MTTD** | Mean Time to Detect — average time from incident start to detection |
| **MTTC** | Mean Time to Contain — average time from detection to containment |
| **MTTR** | Mean Time to Recover — average time from detection to full restoration |

---

## 4. Policy Statements

### 4.1 Incident Response Program Requirement

NexaCore shall maintain a documented, tested, and continuously improved incident response program that addresses the full incident lifecycle: preparation, detection, containment, eradication, recovery, and post-incident activity. This program shall be aligned with NIST SP 800-61 Rev. 3 and the NIST Cybersecurity Framework 2.0.

### 4.2 Incident Response Plan

A current, approved Incident Response Plan (IRP) shall be maintained at all times. The IRP shall define procedures for all significant incident categories, specify roles and responsibilities, and establish communication and escalation requirements. The IRP shall be reviewed at minimum annually and following any Tier 1 (Critical) incident.

### 4.3 Incident Response Team

A Computer Incident Response Team (CIRT) shall be established with clearly defined roles, responsibilities, and decision authority. All CIRT members shall complete annual IR training. On-call coverage shall be maintained for 24/7 response to Tier 1 and Tier 2 incidents.

### 4.4 Incident Classification

All security events shall be triaged and classified into severity tiers as defined in the Incident Response Plan. Classification shall drive response timelines, resource allocation, escalation paths, and communication requirements.

### 4.5 Response Timelines

NexaCore shall meet the following minimum response standards:

| Severity | Initial Triage | Incident Declaration | Containment Target |
|---|---|---|---|
| Critical (T1) | 15 minutes | 30 minutes | 2 hours |
| High (T2) | 30 minutes | 1 hour | 4 hours |
| Medium (T3) | 2 hours | 4 hours | 24 hours |
| Low (T4) | 24 hours | 48 hours | 72 hours |

### 4.6 Documentation Requirements

All incident response activities shall be documented in real time in the designated incident tracking system (ServiceNow Security Operations). Documentation shall include, at minimum: timeline of events, actions taken, personnel involved, systems affected, data potentially exposed, and evidence collected.

### 4.7 Evidence Preservation

Digital evidence shall be collected and preserved in accordance with chain of custody procedures defined in the Incident Response Plan. Evidence integrity shall be maintained using cryptographic hash verification. No evidence shall be deleted, modified, or transferred without written authorization from Legal Counsel.

### 4.8 Regulatory Notification

When an incident triggers a regulatory notification obligation, NexaCore shall notify the applicable authority within the timeframes required by law. Legal Counsel shall be engaged immediately upon identification of any potential regulatory notification obligation.

Applicable notification obligations include:
- **PCI DSS**: Immediate notification to payment brands and acquiring bank upon suspected CHD compromise
- **GLBA Safeguards Rule**: Customer notification within 30 days of discovery
- **State Breach Notification Laws**: Notification within applicable state-specific windows (30–72 hours for most jurisdictions)
- **Contractual Obligations**: Customer notification as specified in service agreements

### 4.9 Confidentiality of Incident Information

Information about security incidents shall be disclosed only on a need-to-know basis. External disclosure of incident information requires approval from Legal Counsel and the Chief Communications Officer. No employee shall communicate incident information to media, customers, or external parties without explicit authorization.

### 4.10 Lessons Learned

A post-incident review shall be conducted for all Tier 1 and Tier 2 incidents within 5 business days of incident closure. Lessons learned shall be documented and translated into actionable improvements to controls, procedures, and detection capabilities. Action items shall be tracked to closure.

### 4.11 Testing and Exercises

The Incident Response Plan shall be tested at minimum once annually through a tabletop exercise or simulation. Testing results shall be documented and used to improve the plan. Additional quarterly tabletop exercises are required.

### 4.12 Third-Party Incidents

NexaCore shall require material third-party service providers with access to NexaCore systems or data to maintain incident response capabilities and to notify NexaCore of any incident affecting NexaCore data within 24 hours of discovery. This requirement shall be included in all vendor contracts.

---

## 5. Roles and Responsibilities

### 5.1 CISO
- Owns the incident response program and this policy
- Approves the Incident Response Plan and all major revisions
- Serves as executive escalation point for Tier 1 incidents
- Reports to the Board Risk Committee on program status and significant incidents
- Authorizes major containment decisions (e.g., production system shutdowns)

### 5.2 Incident Commander
- Leads active incident response operations
- Owns all decisions during an active incident within the authority defined in the IRP
- Serves as primary communication point between CIRT and executive team
- Ensures documentation requirements are met throughout the response

### 5.3 CIRT Members
- Execute incident response procedures per their defined roles
- Maintain current skills through required training program
- Participate in tabletop exercises and simulations
- Document all actions taken during incident response in real time

### 5.4 Legal Counsel
- Advises on regulatory notification obligations
- Manages litigation hold requirements
- Coordinates with law enforcement as appropriate
- Approves external communications related to incidents

### 5.5 All Employees
- Report suspected security incidents to the IT Help Desk or Security Operations Center immediately upon observation
- Cooperate fully with incident response activities
- Maintain confidentiality of incident information
- Complete required annual security awareness and incident reporting training

---

## 6. Incident Reporting

### 6.1 Internal Reporting
All employees, contractors, and service providers shall report suspected security incidents immediately using the following channels:
- **IT Help Desk**: ext. 5000 / helpdesk@nexacore.com
- **Security Operations Center (SOC)**: soc@nexacore.com / security hotline: ext. 5911
- **Direct Manager**: For situations requiring immediate business judgment

Reports should include: what was observed, when it was observed, what systems were affected, and any actions already taken.

### 6.2 Anonymous Reporting
Incidents may also be reported anonymously through the Ethics Hotline. Anonymous reports will be investigated with the same priority as identified reports.

---

## 7. Non-Compliance

Failure to comply with this policy may result in disciplinary action up to and including termination of employment. Deliberate obstruction of incident response activities, destruction of evidence, or unauthorized disclosure of incident information may result in legal action in addition to employment consequences.

---

## 8. Policy Review and Maintenance

This policy shall be reviewed and updated:
- Annually (mandatory)
- Following any Tier 1 security incident
- Upon significant changes to NexaCore's technology environment or business operations
- Upon changes to applicable regulatory requirements
- Upon identification of material gaps during exercises or audits

All revisions require CISO approval. Changes affecting regulatory obligations require Legal Counsel review.

---

## 9. Related Documents

- Incident Response Plan (IRP) — the operational implementation of this policy
- Data Classification Policy (POL-SEC-DC-001)
- Acceptable Use Policy (POL-HR-AUP-001)
- Business Continuity Plan (POL-OPS-BCP-001)
- Vendor Security Requirements Policy (POL-SEC-VEN-001)

---

*NexaCore Technologies, Inc. — POL-SEC-IR-001 v1.0 — Approved April 1, 2026*
