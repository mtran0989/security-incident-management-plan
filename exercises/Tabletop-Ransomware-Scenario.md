# Tabletop Exercise — Ransomware Scenario
## NexaCore Technologies | Exercise TTX-001

| Attribute | Detail |
|---|---|
| **Exercise ID** | TTX-001 |
| **Scenario** | Ransomware — FinTech Targeted Attack |
| **Difficulty** | Advanced |
| **Duration** | 3 hours |
| **Frequency** | Annual (plus quarterly abbreviated version) |
| **Facilitator** | IR Program Manager or external facilitator |
| **Target Participants** | Full CIRT + CISO + Legal + CCO + Finance + IT Infrastructure |
| **Framework** | NIST SP 800-61 Rev. 3 · SANS PICERL |
| **Classification** | Internal Confidential |

---

## Exercise Objectives

By the end of this exercise, participants will have practiced:

1. Rapid incident declaration and severity classification for ransomware
2. Cross-functional coordination and decision-making under pressure
3. Containment decision-making with competing operational and security priorities
4. Regulatory notification obligation assessment and timing
5. Executive communication during a Tier 1 incident
6. Ransom payment decision framework

---

## Pre-Exercise Setup

**Facilitator preparation (2 weeks before):**
- [ ] Distribute pre-reading: PB-001 Ransomware Playbook, current ransomware threat landscape brief
- [ ] Prepare inject timeline (below) and discussion questions
- [ ] Set up simulated incident timeline in ServiceNow (optional for realism)
- [ ] Confirm all role players are assigned and prepared
- [ ] Prepare facilitator notes and expected discussion points for each inject

**Participant preparation:**
- [ ] Review PB-001 Ransomware Playbook
- [ ] Review IR Policy — notification obligations and escalation thresholds
- [ ] Review contact directory — know your escalation contacts

---

## Scenario Background

**THREAT ACTOR:** A ransomware group known as "SilverThread" has been actively targeting FinTech payment processors in North America. SilverThread uses a double-extortion model — encrypting files while simultaneously exfiltrating data and threatening to publish it publicly. Their initial access TTPs include spear-phishing and exploitation of internet-facing VPN vulnerabilities.

**NEXACORE CONTEXT:**
- It is a Tuesday in April, 2:47 AM CST
- NexaCore's on-call SOC analyst is monitoring the environment
- A major client's month-end payment processing cycle is scheduled to begin at 6:00 AM (3 hours away)
- The CISO is traveling internationally and is 7 hours ahead (9:47 AM local)

---

## Exercise Injects

### INJECT 1 — 2:47 AM: Initial Alert
*[Facilitator reads aloud or displays]*

> The on-call SOC analyst receives a Microsoft Defender for Endpoint alert: **"Suspicious mass file modification activity detected on CorpSrv-PROD-12"** — 847 files modified in 4 minutes. A second alert fires: **"Shadow copy deletion via vssadmin.exe detected on CorpSrv-PROD-12."**
>
> CorpSrv-PROD-12 is a production file server in NexaCore's Austin data center, classified as Tier 2 (business-operational). It hosts shared drives used by Finance and Operations teams.

**Discussion Questions:**
1. What is your immediate priority — containment or investigation? Why?
2. What is the initial severity classification? What information would change it?
3. Who do you notify right now, and how?
4. What is your first containment action, and what are the risks?

---

### INJECT 2 — 3:15 AM: Scope Expansion
*[30 minutes after Inject 1]*

> The Lead Incident Analyst, now on call, has run EDR threat hunting queries. Results:
> - 3 additional hosts show mass file modification activity: CorpSrv-PROD-08, CorpSrv-PROD-09, and WSRV-FIN-02
> - WSRV-FIN-02 is a financial reporting server with read access to the payment processing database
> - Ransom notes ("SilverThread_README.txt") have been found on all affected servers
> - Network logs show outbound connections from CorpSrv-PROD-12 to a Mega.nz cloud storage URL beginning 4 hours ago (10:47 PM the previous evening)
>
> **NEW INTEL:** The EDR timeline shows the initial compromise occurred 6 days ago via a phishing email that delivered a malicious document. The attacker has been in the environment for 6 days.

**Discussion Questions:**
1. The attacker was in the environment for 6 days. What does this mean for your containment strategy?
2. WSRV-FIN-02 has access to payment processing data. Does this change your severity classification?
3. The outbound Mega.nz traffic suggests data exfiltration. What regulatory obligations are now potentially triggered?
4. The CISO is overseas and it's 3 AM local time — do you call now? Who makes that decision?

---

### INJECT 3 — 4:00 AM: Executive Pressure
*[45 minutes after Inject 2]*

> The CEO has been reached and is on the call. He states: "The 6 AM payment processing run CANNOT be delayed. We have contractual SLAs with our top 20 clients and missing that window is a $2M penalty. Can we isolate just the affected servers and keep the payment systems running?"
>
> The payment processing servers (CorpSrv-PAY-01 through PAY-04) have NOT shown encryption activity yet, but they are on the same network segment as CorpSrv-PROD-12.
>
> Additionally: Legal Counsel has joined the call and notes that if cardholder data (CHD) was accessed on WSRV-FIN-02, PCI DSS requires immediate notification to the acquiring bank — an action that will trigger a formal PCI investigation.

**Discussion Questions:**
1. How do you respond to the CEO's request? What are the security risks of keeping the payment systems running in the current environment?
2. What is the Incident Commander's authority here versus the CEO's?
3. What does "immediate notification" mean under PCI DSS — does it mean right now, at 4 AM?
4. Who has the authority to confirm whether CHD was actually on WSRV-FIN-02?

---

### INJECT 4 — 5:30 AM: Ransom Demand
*[90 minutes after Inject 3]*

> A ransom note discovered on the encrypted servers demands $4.5M in cryptocurrency within 72 hours for decryption keys. The note includes a sample of what appears to be NexaCore financial data as proof of exfiltration and threatens to publish the full dataset on their leak site.
>
> The CISO, now online, asks the team to assess: "Are any of our backups clean? What is the recovery time if we don't pay?"
>
> IT Infrastructure reports: the most recent confirmed-clean backup of the affected servers is from 8 days ago — 2 days before the estimated initial compromise. 6 days of data may be unrecoverable from backup.

**Discussion Questions:**
1. Walk through the ransom payment decision framework. What factors must be considered?
2. Who has the authority to authorize a ransom payment? What is the process?
3. FBI guidance is to NOT pay ransom, but the organization faces significant data loss. How do you advise the executive team?
4. What are the legal implications of paying ransom? (OFAC sanctions, insurance considerations)
5. How does the 6-day backup gap change the recovery strategy?

---

### INJECT 5 — Day 2: Media and Client Pressure
*[Next morning — 24 hours after initial detection]*

> A technology news outlet has published an article: "NexaCore Technologies suffers ransomware attack — sources say payment data may be compromised." The article includes what appears to be a screenshot of the SilverThread leak site showing NexaCore data.
>
> NexaCore's top 5 clients have all called their account managers demanding information.
>
> One client, a large regional bank, has threatened to invoke their contractual right to immediate audit access to NexaCore systems.

**Discussion Questions:**
1. How did the media find out? What are the possible sources? Does it matter for your response?
2. What do you tell the clients calling now? What is the approved message?
3. Can you refuse the audit access request? Should you?
4. How does the public disclosure change your regulatory notification obligations?

---

## Exercise Debrief Guide

### Metrics to Assess
- Time to initial escalation (Inject 1 → IC notification)
- Clarity of severity classification rationale
- Quality of containment decision-making under operational pressure
- Legal/regulatory obligation awareness
- Executive communication effectiveness
- Ransom decision framework knowledge

### Key Learning Points to Reinforce
1. 6-day dwell time is common — assume the scope is larger than initially visible
2. Containment must be weighed against operational impact, but security recommendations must be clearly documented even if executives choose a different path
3. PCI DSS notification obligations are strict and time-sensitive — Legal must be involved immediately
4. Ransom payment decisions require a formal process: Legal, CISO, CEO, insurance carrier, and FBI consultation
5. Media coverage accelerates all timelines — pre-draft external communications during Preparation phase

---

## After Action Report Template

| Section | Content |
|---|---|
| **Exercise Date** | |
| **Participants** | |
| **Overall Assessment** | [Satisfactory / Needs Improvement / Unsatisfactory] |
| **Strengths Identified** | |
| **Gaps Identified** | |
| **Action Items Generated** | |
| **IRP Updates Required** | |
| **Next Exercise Date** | |

---

*NexaCore Technologies — TTX-001 Ransomware Tabletop v1.0 — April 2026*
