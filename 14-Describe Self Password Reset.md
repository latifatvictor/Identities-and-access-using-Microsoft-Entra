## Self‑Service Password Reset (SSPR)

### 📘 Summary
Self‑service password reset (SSPR) allows users to **reset or change their password without helpdesk involvement**.  
If a user forgets their password or gets locked out, they can reset it using registered authentication methods.

As the documentation states:  
> “SSPR reduces help desk calls and loss of productivity when a user can't sign in.”

SSPR also provides **audit logs** that can be exported to SIEM systems for monitoring and compliance.

---

## 🔧 How SSPR Works
When a user accesses the SSPR portal, Microsoft Entra ID checks:

1. **Is the account valid?**  
2. **Is SSPR enabled for this user?**  
3. **Has the user registered authentication methods?**  
4. **Where is the password managed?** (Cloud or on‑prem AD)  

If all checks pass, the user is guided through password reset or unlock.

### Requirements
Users must:
- Have a valid **Microsoft Entra ID license**  
- Be **enabled for SSPR**  
- Have **registered authentication methods** (preferably two or more)

---

## 🔐 Authentication Methods for SSPR

Users can register the following methods:

- **Microsoft Authenticator push notifications**  
- **Software OATH tokens**  
- **Hardware OATH tokens** (preview)  
- **SMS**  
- **Voice call**  
- **Email OTP**  
- **Security questions** *(retiring March 2027)*  

Administrators choose whether **one** or **two** methods are required.

**Admin accounts:**  
- Always require **two methods**  
- Cannot use security questions  

---

## 🏢 Real‑World Scenarios & Practical Notes

### Scenario 1: User Forgot Password but Still Has Phone
User can’t sign in but still has access to their phone.

**Fix:**  
User completes SSPR using Authenticator, SMS, or voice call.

**Outcome:**  
No helpdesk ticket needed.

---

### Scenario 2: User Lost Phone and Has No Backup Methods
User loses their phone and has no other registered methods.

**SSPR alone is not enough.**

**Solution:**  
Use **Microsoft Entra Account Recovery**, which:  
- Uses Verified ID + Face Check  
- Re-establishes identity without helpdesk  
- Avoids social engineering risks  

---

### Scenario 3: Hybrid Environment with On‑Prem AD
User resets password in the cloud, but on‑prem AD still has old password.

**Solution:**  
Enable **password writeback** via Cloud Sync or Entra Connect.

As the documentation states:  
> “Users… can reset their passwords and have the new password written back on‑premises without delay.”

---

### Scenario 4: User Account Locked Out
User enters wrong password too many times.

**Fix:**  
Enable **unlock without password reset** (optional).  
User unlocks account without changing password.

---

## 🛠 Common IT Tickets You’ll See in This Area

| Ticket | Description | Typical Fix |
|--------|-------------|-------------|
| “I forgot my password” | User lockout | Guide user to SSPR portal |
| “My phone number changed” | Outdated methods | Update authentication methods |
| “Password reset not syncing to AD” | Writeback issue | Check Cloud Sync/Connect health |
| “User can’t register for SSPR” | Not enabled | Enable SSPR + enforce registration |
| “Admin locked out” | Missing second factor | Use TAP or Verified ID recovery |

---

## 🔁 Registration & Reconfirmation

Admins can require:
- **Registration at sign‑in**  
- **Reconfirmation** every 0–730 days  

This ensures authentication methods remain current.

---

## ✉️ Notifications

SSPR sends email alerts:

- Users receive email when their password is reset  
- Global admins receive email when another admin resets their password  

This improves visibility and security.

---

## 🏢 On‑Prem Integration & Password Writeback

With password writeback enabled:
- Cloud password resets sync to on‑prem AD  
- Works for federated, PTA, and PHS users  
- Users can unlock AD accounts without resetting passwords  

If using non‑Microsoft password filters, ensure they support admin‑initiated resets.

---

## 🔄 SSPR vs Account Recovery

| Aspect | Self‑Service Password Reset | Account Recovery |
|--------|------------------------------|------------------|
| Use case | Forgot password | Lost all authentication methods |
| Requirement | At least one registered method | Verified ID identity proofing |
| Scope | Password only | Full authentication method reset |
| Security | Relies on preregistered methods | High‑assurance identity verification |

Account recovery uses **Microsoft Entra Verified ID with Face Check** for secure identity proofing.

---

## 🧩 Troubleshooting Patterns

- Check if user is **licensed**  
- Confirm SSPR is **enabled**  
- Verify user has **registered methods**  
- Review **SSPR audit logs**  
- For hybrid: check **password writeback health**  
- For admins: ensure **two methods** are registered  

---

## 📌 Key Takeaways
- SSPR reduces helpdesk load and improves productivity  
- Users must register authentication methods before using SSPR  
- Password writeback enables hybrid password resets  
- Admin accounts require two methods  
- Account recovery handles total lockout scenarios  
- Verified ID provides secure, AI‑powered identity proofing  

