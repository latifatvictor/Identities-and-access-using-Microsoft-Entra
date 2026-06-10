# 🔐 Microsoft Entra – Conditional Access Lab (Quick Steps)

## 🧪 Exercise: Perform Basic Conditional Access Tasks

⏱ Duration: ~10 minutes  

---

## 🧩 Task 1 – Create Conditional Access Policy

Step 1 > Go to https://entra.microsoft.com  
Step 2 > Log in  
Step 3 > Navigate: Protection > Conditional Access  
Step 4 > Click + Create new policy  
Step 5 > Enter name: Block Bhogeswar from using Sway  

---

### 👤 Assign Users

Step 6 > Select Users and groups  
Step 7 > Include > Select Bhogeswar Kalita  
Step 8 > Exclude > Select admin account  
Step 9 > Confirm selection  

---

### 📱 Select Target Resource

Step 10 > Go to Target resources  
Step 11 > Select Resources (Cloud apps)  
Step 12 > Choose Select resources  
Step 13 > Search and select Sway  
Step 14 > Confirm selection  

---

### 🚫 Configure Access Control

Step 15 > Go to Access controls > Grant  
Step 16 > Select Block access  
Step 17 > Confirm selection  

---

### ✅ Enable Policy

Step 18 > Set Enable policy = On  
Step 19 > Click Create  

---

## 🧩 Task 2 – Perform What If Analysis

Step 1 > Go to Protection > Conditional Access  
Step 2 > Click What If tool  
Step 3 > Select User = Bhogeswar Kalita  
Step 4 > Select Cloud app = Sway  
Step 5 > Click What If  
Step 6 > Review result (Access blocked)  

---

### 🔁 Subtask – Test Different App

Step 1 > Remove Sway  
Step 2 > Select Office 365  
Step 3 > Click What If  
Step 4 > Review result (Policy not applied)  

---


# 🛡 Microsoft Entra – Conditional Access Policy (Summary)

## 📌 Overview
Conditional Access (CA) = **If → Then logic**

✅ Example:
If user signs in → Then require MFA  

Policies combine:
- Assignments (who, what, where)  
- Access controls (block or allow with conditions)  

---

## ⚙️ How Policies Work

✅ Multiple policies can apply at once  
→ ALL must be satisfied (AND logic)

✅ Example:
Policy 1 = Require MFA  
Policy 2 = Require compliant device  
➡ User must complete BOTH  

---

## 🔄 Policy Evaluation Process

### Phase 1 – Collect Data

Step 1 > Gather session details:
- Location  
- Device  
- Risk  

---

### Phase 2 – Enforce Policy

Step 2 > Check requirements  
Step 3 > If Block access → Deny immediately ❌  
Step 4 > Otherwise prompt in order:

- MFA  
- Device compliance  
- Hybrid join  
- Approved app  
- App protection  
- Password change  
- Terms of use  

Step 5 > Apply session controls  

---

## 🧩 Assignments (Who / What / Where)

### 👤 Users & Groups
- All users  
- Specific users/groups  
- Roles (admins)  
- Guests  

✅ Tip:
Exclude admin account to avoid lockout  

---

### 📱 Target Resources
- Cloud apps (e.g. M365, Sway)  
- User actions  

---

### 🌍 Network (Location)
- IP addresses  
- Countries  
- Trusted locations  

---

### ⚙️ Conditions

- Sign-in risk  
- Device platform (Windows, iOS, etc.)  
- Client apps (Browser, Mobile)  
- Device filters  

---

## 🔐 Access Controls

### 🚫 Block Access
- Completely deny access  

---

### ✅ Grant Access (with conditions)

- Require MFA  
- Require compliant device  
- Require hybrid joined device  
- Require approved app  
- Require password change  
- Require terms of use  

---

### 🎯 Control Options

- Require ALL controls ✅  
- Require ONE control (OR logic)  

---

## 🖥 Session Controls

- Limit user session  
- Control access (view only, no download)  
- Monitor activity  

✅ Examples:
- Block downloads  
- Restrict copy/paste  
- Set sign-in frequency  

---

## ✅ Minimum Requirements for Policy

Step 1 > Name policy  
Step 2 > Assign users/groups  
Step 3 > Select target resources  
Step 4 > Configure access control  

---

## ✅ Summary Flow

Define Users > Select App > Set Conditions > Apply Controls > Enforce Policy  

---

## 🧠 Key Takeaways

- Conditional Access = Identity firewall  
- Policies use AND logic  
- Always test with Report-only first  
- Use MFA + device + risk together  
- Multiple policies can apply simultaneously  

---

## 🔐 Security Insight

👉 Strongest setup:
Conditional Access + MFA + Device Compliance  

(Not just one control alone)

## ✅ Summary Flow

Create Policy > Assign User > Target App > Block Access > Enable > Test with What If
