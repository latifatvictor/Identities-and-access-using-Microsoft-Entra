# 🎯 IAM Interview Questions (Microsoft Entra Focus)

## 🔐 1. What is the difference between Authentication and Authorization?

Authentication = Who you are (username/password, MFA)  
Authorization = What you can access (roles, permissions)

✅ Example:
User logs in (Authentication) → Gets access to SharePoint (Authorization)

---

## 👑 2. Why is MFA important?

- Prevents password-based attacks
- Adds second layer of protection

✅ Real Insight:
Most breaches happen due to compromised credentials — MFA stops this.

---

## 🛡 3. What is Conditional Access?

A policy engine that controls access based on:
- User
- Device
- Location
- Risk

✅ Example:
Block access if user logs in outside UK without MFA

---

## ⚖️ 4. What is RBAC?

Role-Based Access Control:
- Assign roles instead of permissions

✅ Example:
User Administrator role can manage users

✅ Best Practice:
Always apply Least Privilege

---

## 👥 5. Why use Groups instead of direct assignments?

- Scalable
- Easier to manage
- Reduces human error

✅ Example:
Assign license to group instead of individual users

---

## 🔄 6. What is JML (Joiner, Mover, Leaver)?

Lifecycle of a user:

Joiner → Create account  
Mover → Change roles/permissions  
Leaver → Disable account  

✅ Key Risk:
Leavers with active access = security risk

---

## 🔑 7. What is SSPR?

Self-Service Password Reset:
- Users reset passwords without IT help

✅ Benefits:
- Reduces helpdesk tickets
- Improves security when combined with MFA

---

## 🔒 8. What is Password Protection?

Prevents weak passwords by:
- Blocking common words
- Enforcing strong policies

✅ Example:
Block “CompanyName123”

---

## 🚨 9. What is the biggest IAM risk?

Compromised identities

✅ Why?
Identity = access to everything

---

## 🧠 10. What is Zero Trust?

“Never trust, always verify”

✅ Principles:
- Verify identity
- Use least privilege
- Assume breach

---

## 🔍 11. How do you avoid locking yourself out?

- Exclude admin from Conditional Access
- Use break-glass account
- Test using Report-only mode

---

## ⚙️ 12. How would you automate IAM?

- PowerShell (Microsoft Graph)
- Dynamic groups
- Group-based licensing

✅ Shows senior-level thinking
