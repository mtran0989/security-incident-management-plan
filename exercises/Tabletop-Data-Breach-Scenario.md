# Tabletop Exercise — Data Breach Scenario
## NexaCore Technologies | Exercise TTX-003

| Attribute | Detail |
|---|---|
| **Exercise ID** | TTX-003 |
| **Scenario** | Data Breach — API Vulnerability & CHD Exfiltration |
| **Difficulty** | Advanced |
| **Duration** | 3 hours |
| **Participants** | Full CIRT + CISO + Legal + CCO + Client Relations |

---

## Scenario Background

A security researcher discovers an authentication bypass vulnerability in NexaCore's payment processing API (v2.3.1). Unknown to NexaCore, a threat actor discovered the same vulnerability 45 days ago and has been silently querying the API to extract cardholder data. The researcher notifies NexaCore's security team at 9:00 AM on a Monday.

---

## Exercise Injects

### INJECT 1 — 9:00 AM: Researcher Notification
> Security researcher "CryptoFox" emails security@nexacore.com with a detailed proof-of-concept demonstrating an authentication bypass in the /v2/payments/query endpoint. The email states: "I have been responsibly sitting on this for 30 days waiting for your bug bounty program to respond. I have not disclosed publicly, but I will in 7 days."

**Discussion:** How do you triage a researcher report? What is the bug bounty program response obligation? Is this an active incident or a vulnerability report?

---

### INJECT 2 — 11:00 AM: Log Analysis Confirms Exploitation
> Analyzing API access logs for the past 90 days (the retention window), analysts find systematic query patterns that could only result from the authentication bypass — 2.3M cardholder records queried over 45 days. The last access was 3 days ago. The exfiltration appears complete.

**Discussion:** 2.3M CHD records. Walk through the PCI DSS notification requirements — who, how fast, and what exactly must be communicated? What is the acquiring bank call going to involve? Who needs to be in the room?

---

### INJECT 3 — 2:00 PM: Client Calls
> Three major clients call their account managers after noticing unusual query patterns in their monthly API reports. One client — a top-10 bank — states their legal team is reviewing whether to invoke their contractual audit rights and potentially terminate the agreement.

**Discussion:** What can you tell clients at 2 PM on day 1 when the investigation is still ongoing? How do you balance transparency with legal risk? Who approves the client communication?

---

### INJECT 4 — Day 3: Regulatory & Media
> VISA has received the acquiring bank notification and opened a formal PCI forensic investigation. A QFIR (Qualified Forensic Investigator Report) is required within 10 business days. Simultaneously, a journalist has contacted NexaCore PR asking for comment on "reports of a major payment data breach."

**Discussion:** How does the PCI forensic investigation interact with NexaCore's own investigation? Does the media inquiry accelerate any disclosure obligations? What is the approved PR response?

---

## Key Learning Points
1. API access logs must be retained for at least 90 days — preferably 12 months
2. PCI DSS CHD breach triggers immediate acquiring bank notification — same-day
3. External researchers deserve timely response to avoid forced disclosure
4. QFIR requirements mean external forensics must be engaged early

---

*NexaCore Technologies — TTX-003 Data Breach Tabletop v1.0 — April 2026*
