# 🔐 Microsoft Entra – Multifactor Authentication (MFA) Lab (Quick Steps)

## 🧪 Exercise: Perform Basic MFA Tasks

⏱ Duration: ~10 minutes  

---

## 🧩 Task 1 – Enable Per-User MFA

Step 1 > Go to https://entra.microsoft.com  
Step 2 > Log in  
Step 3 > Navigate: Identity > Users > All users  
Step 4 > Click Per-user MFA (top menu)  
Step 5 > Select user (Bhogeswar Kalita)  
Step 6 > Click Enable MFA  
Step 7 > Confirm Enable  
Step 8 > Verify status shows Enforced  

---

## 🧩 Task 2 – Review MFA Service Settings

Step 1 > Go to Identity > Users > All users  
Step 2 > Click Per-user MFA  
Step 3 > Select Service settings  
Step 4 > Review configuration options:

- App passwords (for legacy apps)  
- Trusted IPs (bypass MFA for safe locations)  
- Verification options (allowed MFA methods)  
- Remember MFA on trusted devices  

Step 5 > Click Discard (if no changes made)  

---

## 🧩 Task 3 – Configure MFA Account Lockout

Step 1 > Go to Protection  
Step 2 > Click Show more  
Step 3 > Select Multifactor authentication  
Step 4 > Click Account lockout  

Step 5 > Set values:
- MFA denials before lockout = 3  
- Reset counter = 180 minutes  
- Auto-unblock = 15 minutes  

Step 6 > Click Save  

---

## ✅ Summary Flow

Enable MFA > Review Settings > Configure Lockout Protection



# 🔐 Microsoft Entra – Authentication Overview (Summary)

## 📌 Overview
Authentication verifies a user's identity before granting access to:
- Applications  
- Services  
- Devices  
- Networks  

✅ Purpose:
Ensure only authorised users can access resources  

---

## 🔑 Authentication Methods (Key Types)

### ✅ Primary Authentication (Sign-in)
- Password  
- Passkeys (FIDO2)  
- Microsoft Authenticator (passwordless)  
- Windows Hello for Business  
- Certificate-based authentication  

---

### ✅ Secondary Authentication (MFA)

- Microsoft Authenticator (push)  
- SMS / Voice  
- Email OTP  
- OATH tokens (hardware/software)  
- Passkeys (FIDO2)  

---

### ✅ Password Reset / Recovery

- Email OTP  
- SMS  
- Authenticator app  
- Verified ID (identity verification only)  

---

## 🔐 Phishing-Resistant Methods (Best Practice)

✅ Recommended:
- Windows Hello for Business  
- Passkeys (FIDO2)  
- Security keys  
- Certificate-based authentication  

✅ Why:
- Resistant to phishing attacks  
- No shared secrets (like passwords)  

---

## ⚠️ Traditional MFA Limitations

- SMS, Email OTP, push notifications can be phished  
- Users may be tricked into approving requests  

✅ Risk:
Credential + OTP theft via social engineering  

---

## 🧩 Verified ID (Account Recovery)

- Used for identity verification (not login)  
- Can verify with:
  - Government ID  
  - Biometric face match  

✅ Use case:
High-assurance account recovery  

---

## 🛡 High-Assurance Account Recovery

Step 1 > User verifies identity (ID + biometric)  
Step 2 > System validates identity  
Step 3 > User regains account access  

✅ Benefit:
- No helpdesk required  
- Reduces social engineering risk  

---

## ✅ Authentication Flow

User Login  
→ Identity verified  
→ MFA (if required)  
→ Access granted  

---

## 🧠 Key Takeaways

- Authentication = verifying identity  
- MFA adds security but can be phished  
- Use phishing-resistant methods where possible  
- Verified ID supports secure recovery  
- Strong authentication = foundation of Zero Trust  

---

## 🔐 Security Insight

👉 Passwordless + MFA + Conditional Access = Strongest Identity Security  

(Not password-only or SMS-based MFA)
