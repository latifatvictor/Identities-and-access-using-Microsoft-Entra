# 🔐 Microsoft Entra – Password Protection Lab (Quick Steps)

## 🧪 Exercise: Perform Basic Password Protection Tasks

⏱ Duration: ~5 minutes  

---

## 🧩 Task 1 – Configure Password Protection Settings

Step 1 > Go to https://entra.microsoft.com  
Step 2 > Log in to your tenant  
Step 3 > Navigate: Protection > Authentication methods  
Step 4 > Select Password protection  

---

### 🔒 Configure Smart Lockout

Step 5 > Set Lockout threshold = 5  
Step 6 > Set Lockout duration = 30 seconds  

---

### 🚫 Configure Banned Password List

Step 7 > Enable "Enforce custom list" = Yes  
Step 8 > Add banned words:


---

### ✅ Apply Settings

Step 9 > Set Mode = Enforced  
Step 10 > Click Save  

---

## ✅ Summary Flow

Open Password Protection > Configure Lockout > Set Banned Passwords > Enforce Policy


# 🔐 Microsoft Entra – On-Premises Password Protection (Summary)

## 📌 Overview
Microsoft Entra Password Protection helps:
- Prevent weak passwords  
- Block common & predictable words  
- Defend against dictionary attacks  

✅ Uses:
- Global banned password list  
- Custom banned password list  

---

## 🧠 Why It Matters

Users often create weak passwords like:
- Company names  
- Locations  
- Common words  

✅ Result:
These are easy to guess → high security risk  

---

## ⚙️ Prerequisites

- Install Password Protection Proxy Service  
- Install DC Agents (on Domain Controllers)  
- Role: Authentication Administrator  

---

## 🧩 Enable On-Prem Password Protection

Step 1 > Go to https://entra.microsoft.com  
Step 2 > Authentication methods > Password protection  
Step 3 > Enable "Password protection on Windows Server AD"  
Step 4 > Choose Mode (Audit / Enforced)  
Step 5 > Click Save  

---

## 🔄 Modes of Operation

### 🟡 Audit Mode (Recommended First)

Step 1 > Enable Audit Mode  
Step 2 > Monitor event logs  
Step 3 > Review weak password attempts  

✅ Behavior:
- Weak passwords are allowed  
- Events are logged  

✅ Use:
Testing + impact analysis  

---

### 🔴 Enforced Mode (Final State)

Step 1 > Switch Mode = Enforced  
Step 2 > Policy blocks weak passwords  

✅ Behavior:
- Weak passwords are rejected  
- Users see error messages  

✅ Use:
Production security enforcement  

---

## ⚠️ User Experience

- Weak passwords are rejected  
- Standard AD error messages displayed  
- Users may need guidance on secure passwords  

---

## ✅ Summary Flow

Deploy Agents > Enable Feature > Audit Mode > Review Logs > Enforce Policy  

---

## 🧠 Key Takeaways

- Extends cloud password protection to on-prem AD  
- Always start in Audit mode  
- Improves password strength across hybrid environments  
- Helps prevent common password attacks  
- Supports global + custom banned password lists  

---

## 🔐 Security Insight

👉 Password Protection + MFA + Conditional Access = Strong Identity Security  

(Not just password complexity alone)


