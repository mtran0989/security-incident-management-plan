# PB-004 — Credential Compromise & Account Takeover
## Incident Response Playbook | NexaCore Technologies

| Attribute | Detail |
|---|---|
| **Playbook ID** | PB-004 |
| **Incident Category** | Credential Compromise / Account Takeover / Unauthorized Access |
| **Default Severity** | Tier 1–3 depending on account privilege and systems accessed |
| **Last Review** | April 2026 |
| **Owner** | Lead Incident Analyst |

---

## 1. Incident Description

Credential compromise occurs when an attacker obtains valid credentials through phishing, credential stuffing, password spraying, or dark web purchase. Account takeover (ATO) is the subsequent use of those credentials to access NexaCore systems. Severity depends on the privilege level of the compromised account and the systems/data accessed.

---

## 2. Trigger Conditions

- UEBA alert: impossible travel, login from new country/device, anomalous access patterns
- Azure AD Identity Protection: risky sign-in or risky user alert
- MFA fatigue attack detected (multiple MFA push notifications)
- Employee reports they cannot log in (potential account locked out by attacker)
- Dark web credential monitoring alert for NexaCore email/password combination
- Multiple failed logins followed by successful login from anomalous IP
- Privileged account activity outside business hours from unrecognized device

---

## 3. Severity Classification

| Condition | Severity |
|---|---|
| Global Admin / CISO / C-suite account compromised | Critical (T1) |
| Privileged service account or PAM account compromised | Critical (T1) |
| Standard privileged user with access to Tier 1 data | High (T2) |
| Standard user account, no evidence of data access | Medium (T3) |
| Credential found on dark web, no confirmed use | Medium (T3) |

---

## 4. Immediate Actions (First 30 Minutes)

- [ ] Force sign-out of all active sessions for the compromised account (Azure AD)
- [ ] Reset password and require MFA re-enrollment
- [ ] Disable account temporarily if attacker may still have MFA access
- [ ] Notify IC; notify CISO if Tier 1 or T2 account
- [ ] Begin audit of what the account accessed in the past 24–72 hours

---

## 5. Detection & Identification Steps

### 5.1 KQL — Risky Sign-Ins

```
// Azure AD risky sign-ins
SigninLogs
| where RiskLevelDuringSignIn in ("high", "medium")
| where ResultType == 0  // Successful sign-in
| project TimeGenerated, UserPrincipalName, IPAddress, Location, DeviceDetail, RiskLevelDuringSignIn
| order by TimeGenerated desc
```

### 5.2 KQL — Impossible Travel

```
SigninLogs
| where ResultType == 0
| extend Location = tostring(LocationDetails.city)
| summarize Locations = make_set(Location), IPs = make_set(IPAddress) by UserPrincipalName, bin(TimeGenerated, 1h)
| where array_length(Locations) > 1
```

### 5.3 Determine Blast Radius
- What systems did the account have access to?
- What did the account do during the suspected compromise window?
- Were any privileges escalated or new accounts created?
- Were any files accessed, modified, or exfiltrated?

---

## 6. Containment

- [ ] Revoke all active sessions (Azure AD: Revoke-AzureADUserAllRefreshToken)
- [ ] Reset password to a strong, unique value
- [ ] Require MFA re-registration on trusted device
- [ ] Block the attacker's source IP at the firewall and Azure Conditional Access
- [ ] If service account: rotate API keys, secrets, and certificates immediately
- [ ] If privileged account: audit all privileged actions taken during compromise window

---

## 7. Eradication

- [ ] Audit for attacker persistence: new accounts created, group membership changes, MFA method additions
- [ ] Review all applications the account has OAuth grants for — revoke unauthorized grants
- [ ] Confirm no additional accounts compromised using same credential set (spray attack)
- [ ] Remediate the source of credential exposure (phishing, password reuse, etc.)

---

## 8. Recovery

- [ ] Re-enable account with new credentials and verified MFA
- [ ] Brief account owner on the incident and prevention measures
- [ ] If password reuse was the vector: enforce password manager use and MFA for all accounts
- [ ] Consider implementing phishing-resistant MFA (FIDO2 hardware keys) for privileged accounts

---

*PB-004 v1.0 — NexaCore Technologies — April 2026*
