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
