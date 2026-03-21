# Data Classification Policy
## NexaCore Technologies, Inc.

| Attribute | Detail |
|---|---|
| **Document ID** | POL-SEC-DC-001 |
| **Version** | 1.0 |
| **Status** | Approved |
| **Classification** | Internal |
| **Owner** | Chief Information Security Officer (CISO) |
| **Effective Date** | April 1, 2026 |
| **Next Review** | April 1, 2027 |

---

## 1. Purpose

This policy defines how NexaCore Technologies classifies its information assets to ensure appropriate protection, handling, and incident response prioritization. Data classification drives decisions about access controls, encryption requirements, retention, and incident severity assessment.

---

## 2. Classification Tiers

### Tier 1 — Restricted

The highest classification level. Unauthorized disclosure would cause severe harm to NexaCore, its clients, or individuals.

**Examples:**
- Payment card data (PAN, CVV, expiration date, cardholder name) — PCI DSS in scope
- ACH and banking credentials for client accounts
- Social Security Numbers and government-issued ID numbers
- Private cryptographic keys and certificate private keys
- Authentication secrets (passwords, MFA seeds, PAM vault contents)
- M&A, litigation, and attorney-client privileged materials

**Controls Required:**
- Encryption at rest (AES-256) and in transit (TLS 1.2+)
- Access limited to role-based need; MFA required
- No storage on unmanaged endpoints or personal cloud storage
- Logging of all access events
- Incident classification: automatic Tier 1 (Critical) upon suspected unauthorized access

---

### Tier 2 — Confidential

Sensitive business information. Unauthorized disclosure would cause significant harm.

**Examples:**
- Employee PII (SSN, date of birth, compensation, performance records)
- Client contracts, SLAs, and pricing agreements
- Proprietary source code and trade secrets
- Security architecture and vulnerability assessment reports
- Internal financial projections and audit findings

**Controls Required:**
- Encryption at rest and in transit
- Access limited to authorized personnel; MFA recommended
- No sharing externally without Legal/CISO approval
- Incident classification: Tier 2 (High) upon suspected unauthorized access

---

### Tier 3 — Internal

Information intended for NexaCore personnel use only.

**Examples:**
- Internal policies, procedures, and operational documentation
- Employee directory and organizational charts
- Project plans and internal roadmaps
- General business correspondence

**Controls Required:**
- Access restricted to NexaCore employees and authorized contractors
- Not to be shared publicly or with unauthorized third parties
- Incident classification: Tier 3 (Medium) upon suspected unauthorized access

---

### Tier 4 — Public

Information approved for public distribution.

**Examples:**
- Marketing materials, press releases, product documentation
- Published API documentation
- Job postings

**Controls Required:**
- Standard integrity controls
- No special handling required
- Incident classification: Tier 4 (Low) unless integrity violation is detected

---

## 3. Incident Response Impact

Data classification is a primary input into incident severity assessment:

| Data Tier | Unauthorized Access / Exfiltration | Regulatory Trigger |
|---|---|---|
| Restricted (T1) | Automatic Critical (T1) incident | PCI DSS, GLBA, State breach laws |
| Confidential (T2) | High (T2) incident | State breach laws (PII), GLBA |
| Internal (T3) | Medium (T3) incident | Situational |
| Public (T4) | Low (T4) incident | None (integrity only) |

---

## 4. Data Owner Responsibilities

Every data asset must have an assigned **Data Owner** (typically a business unit leader) who is responsible for:
- Classifying data assets under their control
- Reviewing and updating classifications annually
- Approving access requests for Tier 1 and Tier 2 data
- Participating in incident response activities involving their data

---

*NexaCore Technologies, Inc. — POL-SEC-DC-001 v1.0 — April 1, 2026*
