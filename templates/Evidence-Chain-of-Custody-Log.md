# Evidence Chain of Custody Log
## NexaCore Technologies — Computer Incident Response Team

> **LEGAL NOTICE: This log constitutes official evidence documentation. Entries must be made in real time. No entry may be altered or deleted after creation. Any correction must be made as a new entry noting the correction.**

---

## Incident Information

| Field | Value |
|---|---|
| **Incident ID** | INC-[YYYY]-[NNNN] |
| **Incident Category** | |
| **Evidence Custodian** | Name / Title |
| **Evidence Storage Location** | Azure Immutable Storage — INC-[YYYY]-[NNNN] container |
| **Log Created** | Timestamp (UTC) |

---

## Evidence Collection Log

| Evidence ID | Timestamp (UTC) | Collected By | Evidence Type | Source System / Location | Description | Collection Method | SHA-256 Hash | Storage Location |
|---|---|---|---|---|---|---|---|---|
| EV-001 | | | Memory (RAM) | | | Magnet RAM Capture | | |
| EV-002 | | | Disk Image | | | FTK Imager | | |
| EV-003 | | | Network PCAP | | | Azure Network Watcher | | |
| EV-004 | | | Log Export (SIEM) | | | Sentinel export | | |
| EV-005 | | | EDR Telemetry | | | Defender for Endpoint | | |
| EV-006 | | | Cloud Audit Logs | | | Azure Activity Log export | | |
| EV-007 | | | Email Artifacts | | | Exchange Online export | | |

---

## Evidence Transfer Log

> *Every time evidence changes custody, a new entry must be made signed by both the transferring and receiving party.*

| Transfer ID | Timestamp (UTC) | Evidence IDs Transferred | Transferred From | Transferred To | Purpose | Transferring Signature | Receiving Signature |
|---|---|---|---|---|---|---|---|
| TR-001 | | | | | | | |

---

## Evidence Access Log

> *Every access to evidence must be logged, including read-only access for analysis.*

| Timestamp (UTC) | Evidence ID | Accessed By | Purpose | Actions Taken | Duration |
|---|---|---|---|---|---|
| | | | | | |

---

## Integrity Verification Log

> *Hash verification must be performed at collection and at each transfer. Record results here.*

| Timestamp (UTC) | Evidence ID | Verified By | Hash Algorithm | Expected Hash | Computed Hash | Match (Y/N) | Notes |
|---|---|---|---|---|---|---|---|
| | | | SHA-256 | | | | |

---

## Evidence Disposition

> *Completed at case closure. Retention: minimum 7 years or per Legal Counsel direction.*

| Evidence ID | Disposition | Date | Authorized By | Notes |
|---|---|---|---|---|
| | Retained — Long-term archive | | | |
| | Returned to owner | | | |
| | Securely destroyed | | | |

---

## Chain of Custody Attestation

I attest that the evidence documented in this log was collected, handled, and stored in accordance with NexaCore's evidence handling procedures and that the integrity of all evidence has been maintained.

**Evidence Custodian:**

Name: _________________________________

Title: _________________________________

Signature: _________________________________

Date: _________________________________

---

*NexaCore Technologies — Evidence Chain of Custody Log v1.0 — April 2026*
*CONFIDENTIAL — Legal Hold Material*
