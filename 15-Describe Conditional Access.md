## Conditional Access (CA) in Microsoft Entra ID

### 📘 Summary
Conditional Access is Microsoft Entra ID’s **Zero Trust policy engine**.  
It evaluates real‑time signals (user, device, location, risk, app, session) and enforces access decisions such as MFA, device compliance, or blocking access.

As the documentation states:  
> “Conditional Access policies are if‑then statements: if a user wants to access a resource, then they must complete an action.”

Conditional Access is enforced **after first‑factor authentication**, meaning it is not a frontline defence against DoS attacks — but it uses signals from such events to make access decisions.

---

## 🧩 Conditional Access Policy Components

A CA policy has two major parts:

### 1. **Assignments** (Who, What, Where, When)
Assignments are logically **ANDed** — all must be true for the policy to apply.

- **Users**  
  Target all users, specific groups, guests, directory roles, or workload identities (including AI agents).

- **Target Resources**  
  Cloud apps (e.g., Microsoft 365), user actions (e.g., register security info), authentication context, or Global Secure Access profiles.

- **Network**  
  Trusted locations, IP ranges, named locations, compliant networks.

- **Conditions**  
  - Sign‑in risk  
  - User risk  
  - Insider risk  
  - Device platform  
  - Client apps  
  - Device filters (e.g., privileged access workstations)

---

### 2. **Access Controls** (What to Do)
Once assignments match, CA enforces one of the following:

- **Block access**  
- **Grant access**, optionally requiring:
  - MFA  
  - Authentication strength  
  - Compliant device  
  - Hybrid joined device  
  - Approved client app  
  - App protection policy  
  - Password change  
  - Terms of use acceptance  

- **Session controls**  
  - Conditional Access App Control (block download/copy/print)  
  - Sign‑in frequency  
  - App‑enforced restrictions  

---

## 🔐 Authentication Strengths
Authentication strengths define **which authentication methods** are allowed.

### Built‑in strengths:
- **Multifactor authentication strength**  
  (Password + SMS/voice/OATH/push)

- **Passwordless MFA strength**  
  (Authenticator phone sign‑in, FIDO2, WHfB)

- **Phishing‑resistant MFA strength**  
  (WHfB, FIDO2, CBA)

Admins can also create **custom strengths** to enforce exact combinations.

---

## 🤖 Protecting AI Services with Conditional Access
As organizations adopt AI tools like Microsoft 365 Copilot and Security Copilot, CA can:

- Require **phishing‑resistant MFA**  
- Require **compliant devices** when insider risk is moderate  
- **Block access** when insider risk is high  

These controls apply to AI service principals just like any other enterprise app.

---

## 🏢 Real‑World Scenarios & Practical Notes

### Scenario 1: Require MFA Only When Off Corporate Network
**Policy:**  
If user is outside trusted IP ranges → require MFA.

**Why:**  
Reduces MFA fatigue while maintaining Zero Trust.

---

### Scenario 2: Block Legacy Authentication
Legacy protocols (IMAP, POP, SMTP AUTH) bypass MFA.

**Policy:**  
Block legacy authentication client apps.

**Outcome:**  
Stops 99% of password spray attacks.

---

### Scenario 3: Protect Admin Roles with Phishing‑Resistant MFA
**Policy:**  
Admins must use FIDO2 or Windows Hello for Business.

**Outcome:**  
Prevents credential theft and MFA phishing.

---

### Scenario 4: Require Compliant Device for Sensitive Apps
Example: Finance team accessing SAP or Dynamics 365.

**Policy:**  
Require device compliance + app protection policy.

---

### Scenario 5: Guest Access Restrictions
**Policy:**  
Guests must complete MFA + cannot download sensitive files.

---

## 🛠 Common IT Tickets You’ll See in This Area

| Ticket | Description | Typical Fix |
|--------|-------------|-------------|
| “User blocked by Conditional Access” | Policy misconfiguration | Check sign‑in logs |
| “MFA required unexpectedly” | Location/device mismatch | Validate trusted locations |
| “Guest user cannot access app” | CA blocking guests | Adjust assignments |
| “App not working on mobile” | Client app condition | Allow mobile apps or use approved apps |
| “Admin cannot sign in” | Strong MFA required | Ensure FIDO2/WHfB registered |

---

## 🧩 Troubleshooting Patterns

- Always start with **Sign‑in Logs → Conditional Access**  
- Check **What If** tool to simulate policy impact  
- Validate:
  - User risk  
  - Sign‑in risk  
  - Device compliance  
  - Network location  
  - Client app type  
- Review **policy order** (CA policies are not ordered, but overlapping policies can stack)  
- Use **report‑only mode** before enforcing new policies  

---

## 🔒 Licensing Requirements
Conditional Access requires:
- **Microsoft Entra ID P1** (core CA)  
- **Microsoft Entra ID P2** (risk‑based CA, identity protection)  

Free-tier tenants can use **security defaults** for basic MFA enforcement.

---

## 📌 Key Takeaways
- Conditional Access is the core of Microsoft’s Zero Trust model  
- Policies evaluate real‑time signals to enforce access decisions  
- Authentication strengths allow granular control over MFA methods  
- CA protects modern workloads, including AI services  
- Sign‑in logs and the What If tool are essential for troubleshooting  
- CA requires Entra ID P1/P2 licensing  

