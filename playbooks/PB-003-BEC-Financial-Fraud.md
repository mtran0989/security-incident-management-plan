# PB-003 — Business Email Compromise & Financial Fraud
## Incident Response Playbook | NexaCore Technologies

| Attribute | Detail |
|---|---|
| **Playbook ID** | PB-003 |
| **Incident Category** | Business Email Compromise (BEC) / Wire Fraud / ACH Fraud |
| **Default Severity** | Tier 1–2 |
| **Last Review** | April 2026 |
| **Owner** | Lead Incident Analyst |

---

## 1. Incident Description

BEC involves threat actors compromising or spoofing email accounts to manipulate employees into authorizing fraudulent financial transfers. For NexaCore, this represents a direct financial threat and potential compromise of client payment infrastructure. BEC actors frequently impersonate executives (CEO fraud), finance leaders, or trusted vendors.

---

## 2. Trigger Conditions

- Finance team reports a suspicious wire transfer request via email
- Employee reports receiving email from executive requesting unusual financial action
- IT reports suspicious inbox rules (forwarding rules to external address) on executive mailbox
- Defender for O365 alert: anomalous login to executive or finance mailbox
- UEBA alert: unusual email forwarding configuration
- Bank or client reports a fraudulent transfer linked to NexaCore email

---

## 3. Immediate Actions (First 15 Minutes)

- [ ] **CRITICAL**: Immediately contact Finance to freeze or recall any pending wire transfers
- [ ] Notify IC and CISO via phone
- [ ] Engage Legal Counsel immediately — BEC triggers financial fraud reporting obligations
- [ ] Preserve the suspicious email (do NOT delete; export headers and body)
- [ ] Identify the mailbox(es) involved: compromised, spoofed, or both?
- [ ] Disable suspicious inbox rules immediately

---

## 4. Detection & Identification Steps

### 4.1 Audit Mailbox for Compromise Indicators

```powershell
# Check for inbox rules forwarding to external addresses
Get-InboxRule -Mailbox "suspect@nexacore.com" | Where-Object {$_.ForwardTo -ne $null -or $_.RedirectTo -ne $null}

# Review recent mailbox login activity
Search-UnifiedAuditLog -StartDate (Get-Date).AddDays(-30) -EndDate (Get-Date) -UserIds "suspect@nexacore.com" -Operations "MailboxLogin" | Select-Object CreationDate, UserIds, ClientIP
```

### 4.2 KQL — Sentinel: BEC Indicators

```
// Suspicious inbox rules
OfficeActivity
| where Operation == "New-InboxRule" or Operation == "Set-InboxRule"
| where Parameters has "ForwardTo" or Parameters has "RedirectTo"
| where Parameters has_any ("gmail", "outlook.com", "yahoo", "protonmail")
| project TimeGenerated, UserId, Parameters, ClientIP
```

### 4.3 Confirm Financial Impact
- Obtain wire transfer details: amount, destination account, initiation timestamp
- Contact NexaCore's bank immediately to attempt recall — time-critical (within 24–72 hours for best chance of recovery)
- Document all fraudulent transactions with full details

---

## 5. Containment

- [ ] Freeze all pending outgoing wire transfers pending review
- [ ] Reset credentials for compromised mailbox(es): password + MFA re-enrollment
- [ ] Remove all unauthorized inbox rules
- [ ] Block external attacker-controlled domains in email security gateway
- [ ] Enable mailbox audit logging if not already active
- [ ] Require out-of-band verification for all financial transfers above $10,000 until cleared

---

## 6. Eradication

- [ ] Confirm no additional compromised mailboxes using the same attacker infrastructure
- [ ] Review all sent items and deleted items from the compromised mailbox for the prior 90 days
- [ ] Audit all financial transactions initiated by email for the prior 30 days
- [ ] Verify MFA is enforced on all finance and executive mailboxes
- [ ] Implement conditional access policy requiring compliant device for finance team logins

---

## 7. Recovery

- [ ] Work with bank/Legal to attempt wire recall
- [ ] Notify cyber insurance carrier — most policies cover BEC losses
- [ ] Restore normal financial operations with enhanced verification controls
- [ ] Brief Finance team on updated transfer verification procedures

---

## 8. Regulatory & Reporting Obligations

- FBI IC3 (Internet Crime Complaint Center): File complaint at ic3.gov within 24 hours
- FinCEN: Suspicious Activity Report (SAR) may be required if financial institution is involved
- Cyber insurance: Notify within 24 hours for potential fraud loss coverage
- Affected clients: Notify if client funds or data were involved

---

*PB-003 v1.0 — NexaCore Technologies — April 2026*
