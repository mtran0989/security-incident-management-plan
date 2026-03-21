# Regulatory & Contractual Notification Matrix
## NexaCore Technologies | Reference Document

> **This document is for reference only. All notification decisions must be made in consultation with Legal Counsel. Regulatory requirements change; verify current requirements with Legal before initiating any notification.**

---

## Notification Requirements by Regulation

### PCI DSS 4.0 — Payment Card Industry Data Security Standard

| Element | Requirement |
|---|---|
| **Trigger** | Actual or suspected compromise of cardholder data (CHD) |
| **Notify** | Acquiring bank AND applicable payment brands (Visa, Mastercard, Amex, Discover) |
| **Timeline** | Immediately upon suspicion — do not wait for confirmation |
| **Content** | Date of discovery, scope of suspected compromise, affected card ranges, contact information |
| **Consequence of non-compliance** | Fines up to $100,000/month, card acceptance termination, mandatory forensic audit |
| **NexaCore Contact** | Legal Counsel + CISO → Acquiring Bank (name/contact in Contact Directory) |

---

### GLBA Safeguards Rule (16 CFR Part 314)

| Element | Requirement |
|---|---|
| **Trigger** | Unauthorized acquisition of unencrypted customer financial information affecting ≥500 customers |
| **Notify** | Federal Trade Commission (FTC) AND affected customers |
| **Timeline** | FTC: within 30 days of discovery; Customer: within reasonable time |
| **Content** | Description of the breach, types of information involved, contact information, steps taken |
| **NexaCore Contact** | Legal Counsel → FTC notification portal |

---

### State Breach Notification Laws (Key Jurisdictions)

| State | Trigger | Timeline | Notify |
|---|---|---|---|
| **California (CCPA/AB 1877)** | Unencrypted PII of CA residents | 72 hours to AG if >500 residents; reasonable time to individuals | CA AG + individuals |
| **New York (SHIELD Act)** | Private information of NY residents | "In the most expedient time possible" | AG + individuals |
| **Texas** | Sensitive personal information of TX residents | 60 days | Individuals; AG if >250 residents |
| **Illinois** | Personal information of IL residents | "Expedient" | Individuals; AG if >500 residents |
| **Federal (CISA — CIRCIA)** | Significant cyber incidents; ransomware payments | 72 hours (incident) / 24 hours (ransom payment) | CISA |

> **Note:** NexaCore operates nationally. Legal Counsel must assess which state laws apply based on the residency of affected individuals. Most incidents trigger multiple state obligations simultaneously.

---

### Cyber Insurance Requirements

| Element | Requirement |
|---|---|
| **Trigger** | Any Tier 1 incident; any incident with potential claim |
| **Notify** | Carrier's incident reporting line (see Contact Directory) |
| **Timeline** | Within 24 hours of Tier 1 incident declaration |
| **Impact of non-notification** | May void coverage for the incident |
| **NexaCore Contact** | CISO → Carrier hotline |

---

### Contractual Client Notification Requirements

| Client Type | Trigger | Timeline | Process |
|---|---|---|---|
| Enterprise clients (standard MSA) | Incident affecting client data | As specified in MSA (typically 72 hours) | Legal + Client Relations |
| PCI merchant clients | CHD compromise | Immediately | Legal + CISO → Acquiring bank → Client |
| Government/regulated clients | Any incident affecting client data | Per contract; often 24–48 hours | Legal review required |

---

## Decision Tree: Do We Need to Notify?

```
Was data accessed or potentially accessed?
  └── NO → No notification required (document determination)
  └── YES → Was the data encrypted with keys not compromised?
        └── YES → Likely no notification required (document determination)
        └── NO / UNKNOWN → Engage Legal Counsel immediately

If notification required:
  ├── CHD involved? → PCI DSS: SAME DAY to acquiring bank
  ├── GLBA-covered customer data? → FTC within 30 days
  ├── PII of individuals? → Assess state laws by residency
  ├── CIRCIA threshold met? → CISA within 72 hours
  └── Ransomware payment made? → CISA within 24 hours
```

---

*NexaCore Technologies — Regulatory Notification Matrix v1.0 — April 2026*
*For reference only — verify with Legal Counsel before any notification action*
