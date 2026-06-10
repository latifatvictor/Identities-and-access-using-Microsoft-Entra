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

## ✅ Summary Flow

Create Policy > Assign User > Target App > Block Access > Enable > Test with What If
