## Microsoft Entra ID Protection

### 📘 Summary
Microsoft Entra ID Protection helps organizations **detect, investigate, and remediate identity-based risks** across:
- User identities  
- Workload identities (apps, service principals, managed identities)

It uses Microsoft’s global intelligence — trillions of signals per day — to identify suspicious activity such as:
- Leaked credentials  
- Password spray attacks  
- Anonymous IP usage  
- Atypical travel  
- Suspicious sending patterns  

ID Protection integrates with Conditional Access to **automate remediation** and can export data to SIEM tools for deeper investigation.

---

## 🧩 How Microsoft Entra ID Protection Works

ID Protection operates across three pillars:

### 1. **Detect Risks**
Microsoft continuously updates its detection catalog using signals from:
- Microsoft Entra ID  
- Microsoft Accounts  
- Xbox gaming network  
- Global threat intelligence  

ID Protection generates two types of risk:

#### **Sign-in Risk**
Probability that a sign-in attempt is not legitimate.  
Examples:
- Anonymous IP address  
- Impossible travel  
- Unfamiliar sign-in properties  
- Malware-linked IP  

#### **User Risk**
Probability that the identity itself is compromised.  
Examples:
- Leaked credentials  
- Suspicious sending patterns  
- User-reported suspicious activity  

> ID Protection only flags events where **correct credentials** were used — because incorrect credentials do not indicate compromise.

---

### 2. **Investigate Risks**
ID Protection provides three key reports:

#### **Risk Detections**
Every individual risk event detected.

#### **Risky Sign-ins**
Sign-ins with one or more associated risk detections.

#### **Risky Users**
Users flagged due to:
- One or more risky sign-ins  
- One or more user risk detections  

These reports help identify weak points in identity security.

---

### 3. **Remediate Risks**
Remediation can be:

#### **Automated (Recommended)**
Using **risk-based Conditional Access**, organizations can require:
- MFA  
- Strong authentication  
- Secure password reset  

If the user completes the required action, the risk is **automatically remediated**.

#### **Manual**
Admins can:
- Dismiss  
- Confirm safe  
- Confirm compromise  

Manual remediation is done via:
- Entra portal  
- Microsoft Graph API  
- Microsoft Defender XDR  

---

## 📤 Exporting Risk Data

ID Protection data can be exported to:
- SIEM tools  
- Log Analytics workspaces  
- Storage accounts  
- Event Hubs  
- Custom monitoring solutions  

This enables long-term retention, correlation, and advanced threat hunting.

---

## 🏢 Real‑World Scenarios & Practical Notes

### Scenario 1: Password Spray Attack Detected
Multiple users show sign-in attempts from the same IP.

**Solution:**  
Risk-based CA → require MFA or block access → force password reset.

---

### Scenario 2: Leaked Credentials Found on the Dark Web
A user risk detection appears for leaked credentials.

**Solution:**  
Require secure password reset → risk remediated automatically.

---

### Scenario 3: Impossible Travel Event
User signs in from London and then from Singapore 2 minutes later.

**Solution:**  
Sign-in risk policy → require MFA → block if MFA fails.

---

### Scenario 4: Compromised Workload Identity
A service principal shows suspicious token usage.

**Solution:**  
Investigate token issuance → rotate secrets/keys → restrict permissions.

---

### Scenario 5: High-Risk User Accessing Sensitive App
A user with elevated user risk attempts to access a finance application.

**Solution:**  
Conditional Access → block access until risk is remediated.

---

## 🛠 Common IT Tickets You’ll See in This Area

| Ticket | Description | Typical Fix |
|--------|-------------|-------------|
| “User blocked due to risk” | Risk-based CA triggered | User completes MFA or password reset |
| “Why am I asked to reset my password?” | User risk detected | Explain risk remediation |
| “Service principal flagged as risky” | Workload identity compromise | Rotate credentials + review logs |
| “Impossible travel detected” | Suspicious sign-in | Validate user activity |
| “SIEM missing risk data” | Export misconfigured | Check diagnostic settings |

---

## 🧩 Troubleshooting Patterns

- Check **Risky Users** and **Risky Sign-ins** reports  
- Review **risk detections** for root cause  
- Validate **Conditional Access** risk policies  
- Confirm user completed remediation steps  
- For workload identities, rotate secrets and review app permissions  
- Export logs to SIEM for deeper analysis  

---

## 📌 Key Takeaways
- ID Protection detects identity-based risks using global intelligence  
- Supports both user and workload identities  
- Risk-based Conditional Access automates remediation  
- Reports provide visibility into risky users and sign-ins  
- Export capabilities support SIEM integration and long-term analysis  
- Essential for Zero Trust and identity threat detection  

