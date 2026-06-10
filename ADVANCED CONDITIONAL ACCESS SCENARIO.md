# 🛡 Advanced Conditional Access Scenario – Zero Trust Architecture

## 📌 Scenario
Your organisation is adopting a **Zero Trust security model**.  

Goal:
✅ Secure access to Microsoft 365 applications  
✅ Protect against credential compromise  
✅ Enforce least privilege + strong authentication  

---

## 🎯 Objective

Design a Conditional Access strategy that:
- Enforces MFA for all users  
- Blocks risky sign-ins  
- Restricts access to compliant devices only  
- Applies stronger controls to admins  
- Allows secure access from trusted locations  

---

## 🏗 Zero Trust Design Principles

- Never trust, always verify  
- Assume breach  
- Use least privilege  
- Verify explicitly (MFA, device, risk)  

---

## 🧩 Policy 1 – Require MFA for All Users

Step 1 > Go to Protection > Conditional Access  
Step 2 > Create New Policy  
Step 3 > Assign: All users (exclude break-glass account)  
Step 4 > Target: All cloud apps  
Step 5 > Grant: Require MFA  
Step 6 > Enable policy  

✅ Outcome:
All users must use MFA  

---

## 🧩 Policy 2 – Block Legacy Authentication

Step 1 > Create New Policy  
Step 2 > Assign: All users  
Step 3 > Conditions > Client apps  
Step 4 > Select Legacy authentication  
Step 5 > Grant: Block access  
Step 6 > Enable policy  

✅ Outcome:
Stops basic auth attacks  

---

## 🧩 Policy 3 – Require Compliant Devices

Step 1 > Create New Policy  
Step 2 > Assign: All users  
Step 3 > Conditions > Device state  
Step 4 > Include: All devices  
Step 5 > Grant: Require device to be compliant  
Step 6 > Enable  

✅ Outcome:
Only managed devices allowed  

---

## 🧩 Policy 4 – Block High-Risk Sign-ins

Step 1 > Create New Policy  
Step 2 > Assign: All users  
Step 3 > Conditions > Sign-in risk  
Step 4 > Set risk level: High  
Step 5 > Grant: Block access  
Step 6 > Enable  

✅ Outcome:
Stops compromised accounts immediately  

---

## 🧩 Policy 5 – Admin Protection (Privileged Users)

Step 1 > Create New Policy  
Step 2 > Assign: Directory roles (Admins)  
Step 3 > Target: All cloud apps  
Step 4 > Grant:
- Require MFA  
- Require compliant device  
Step 5 > Enable  

✅ Outcome:
Extra protection for admins  

---

## 🧩 Policy 6 – Location-Based Access (Trusted Locations)

Step 1 > Create Named location (e.g. Office IP)  
Step 2 > Create New Policy  
Step 3 > Assign: All users  
Step 4 > Conditions > Location  
Step 5 > Include: Any location  
Step 6 > Exclude: Trusted locations  
Step 7 > Grant: Require MFA  
Step 8 > Enable  

✅ Outcome:
Extra security outside office network  

---

## 🔍 Testing Strategy (Critical)

Step 1 > Set policies to Report-only first  
Step 2 > Use What If tool  
Step 3 > Test with different:
- Users  
- Locations  
- Devices  
Step 4 > Review results  
Step 5 > Gradually enable policies  

✅ Prevents accidental lockouts  

---

## 🚨 Break-Glass Account (Critical Safety)

- Create emergency admin account  
- Exclude from all CA policies  
- No MFA enforcement  
- Monitor usage  

✅ Prevents total lockout  

---

## 📊 Final Architecture Flow

User Login → Identity Verified → Risk Checked → Device Evaluated → Policy Applied → Access Granted/Blocked  

---

## ✅ Security Outcomes

✅ Strong identity verification (MFA everywhere)  
✅ Reduced attack surface (no legacy auth)  
✅ Device trust enforced  
✅ Risk-based access control  
✅ Admin accounts hardened  

---

## 🧠 Key Insight

👉 Conditional Access = Identity Firewall  

It evaluates:
- Who (user)  
- Where (location)  
- How (device)  
- Risk level  

Before granting access  

---

## 🚀 Advanced Tip

The strongest setup is:

MFA + Conditional Access + Identity Protection  

NOT just one of them  

---

## ⭐ Why This Matters

This design demonstrates:
✅ Zero Trust implementation  
✅ Enterprise-level IAM thinking  
✅ Security-first mindset  
✅ Real-world architecture skills  
