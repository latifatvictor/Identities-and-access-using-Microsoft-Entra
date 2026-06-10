# 🔐 Microsoft Entra – Group Management Lab (Quick Steps)

## 🧪 Exercise: Perform Basic Group Management Tasks

⏱ Duration: ~15 minutes  

---

## 🧩 Task 1 – Create Microsoft 365 Group

Step 1 > Go to https://entra.microsoft.com  
Step 2 > Log in  
Step 3 > Navigate: Groups > All groups  
Step 4 > Click New group  
Step 5 > Select Group type: Microsoft 365  
Step 6 > Enter name (Project23) & description  
Step 7 > Set Membership type: Assigned  
Step 8 > Add member (Bhogeswar Kalita)  
Step 9 > Click Create  

---

## 🧩 Task 2 – Create Security Group (Dynamic)

Step 1 > Go to Groups > All groups  
Step 2 > Click New group  
Step 3 > Select Group type: Security  
Step 4 > Enter name (Guest Users) & description  
Step 5 > Set Membership type: Dynamic User  
Step 6 > Click Add dynamic query  
Step 7 > Set rule: userType Equals Guest  
Step 8 > Save query  
Step 9 > Click Create  
Step 10 > Refresh group list and verify members  

---

## 🧩 Task 3 – Add User to Group

Step 1 > Go to Groups > All groups  
Step 2 > Select Project23 group  
Step 3 > Click Members  
Step 4 > Click + Add members  
Step 5 > Select External User  
Step 6 > Click Select  

### 🔁 Alternate Method
Step 1 > Go to Users > All users  
Step 2 > Select External User  
Step 3 > Go to Groups  
Step 4 > Click + Add memberships  
Step 5 > Select Project23 group  
Step 6 > Click Select  

---

## 🧩 Task 4 – Add Owners & Licenses

### 👤 Add Owner
Step 1 > Go to Groups > All groups  
Step 2 > Select Project23  
Step 3 > Click Owners  
Step 4 > Click + Add owners  
Step 5 > Select Bhogeswar  
Step 6 > Click Select  

---

### 📄 Assign License to Group
Step 1 > Go to https://admin.microsoft.com  
Step 2 > Navigate: Billing > Licenses  
Step 3 > Select license (e.g. Power Automate Free)  
Step 4 > Go to Groups tab  
Step 5 > Click + Assign licenses  
Step 6 > Select Project23 group  
Step 7 > Click Assign  
Step 8 > Refresh to confirm  

---

## ✅ Summary Flow

Create M365 Group > Create Security Group > Add Members > Assign Owner > Assign License

``


# 👥 Microsoft Entra – Group Management (Summary)

## 📌 Overview
Microsoft Entra groups are used to:
- Manage user access at scale  
- Assign permissions to multiple users at once  
- Simplify access control using groups instead of individuals  

✅ Principle:
Assign access to groups → not users  

---

## ✅ Prerequisites

- Role: User Administrator or Groups Administrator  
- Microsoft Entra tenant  
- Azure subscription (for full features)  

---

## 🧩 Create a Group + Add Members

Step 1 > Entra > Groups > All groups  
Step 2 > Click New group  
Step 3 > Select group type (M365 / Security)  
Step 4 > Enter:
- Group name  
- Description  
Step 5 > Choose Membership type  
Step 6 > Add Members / Owners (optional)  
Step 7 > Click Create  

✅ Result:
Group created with assigned users  

---

## ➕ Add Members / Owners

Step 1 > Groups > Select group  
Step 2 > Click Members or Owners  
Step 3 > Click + Add  
Step 4 > Select users  
Step 5 > Click Select  

✅ Tip:
You can add multiple users at once  

---

## ➖ Remove Members / Owners

Step 1 > Groups > Select group  
Step 2 > Click Members or Owners  
Step 3 > Select user  
Step 4 > Click Remove  

✅ Result:
User loses access linked to group  

---

## ⚙️ Edit Group Settings

Step 1 > Groups > Select group  
Step 2 > Click Properties  
Step 3 > Update:
- Name  
- Description  
- Membership type  
Step 4 > Save  

⚠️ Note:
You cannot change group type after creation  

---

## 🔗 Add Group to Another Group (Nested Groups)

Step 1 > Groups > Select child group  
Step 2 > Click Group memberships  
Step 3 > Click + Add memberships  
Step 4 > Select parent group  
Step 5 > Confirm  

✅ Result:
Child group inherits parent group access  

⚠️ Limitations:
- No license inheritance  
- Not supported for all group types  

---

## 🔓 Remove Group from Another Group

Step 1 > Groups > Select group  
Step 2 > Group memberships  
Step 3 > Select parent group  
Step 4 > Click Remove  

✅ Result:
Inherited access removed  

---

## ❌ Delete a Group

Step 1 > Groups > All groups  
Step 2 > Select group  
Step 3 > Click Delete  

✅ Use cases:
- Duplicate group  
- Incorrect configuration  
- No longer needed  

---

## 🔁 Group Lifecycle Flow

Create Group > Add Members > Assign Access > Maintain > Remove/Delete  

---

## 🧠 Key Takeaways

- Groups simplify access management  
- Use groups for RBAC + licensing  
- Prefer groups over direct assignments  
- Use dynamic groups for automation  
- Clean up unused groups regularly  
``
