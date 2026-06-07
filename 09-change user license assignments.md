## Change User License Assignments

### 📘 Summary
Individual user license assignments are managed through the **Microsoft 365 admin center**, not directly in Microsoft Entra ID.  
This exercise covers:
- Creating a new user  
- Setting usage location  
- Assigning licenses directly to a user  
- Verifying license assignment  

Direct license assignment is still used in many organizations, especially for exceptions, contractors, or users who don’t fit into group-based licensing models.

---

## 🧪 Lab Steps (Condensed)

### 1. Create a New User
- Go to **Identity → Users → All Users → + New User**  
- Create user:  
  - Username: `DominiqueK`  
  - Name: **Dominique Koch**  
  - Password: unique temporary password  
  - Usage location: your preferred region  
- Verify Dominique appears in **All Users**

### 2. Assign License to the User
- Go to **Microsoft 365 Admin Center → Billing → Licenses**  
- Select a license SKU  
- Select **Licensed users**  
- Choose **+ Assign licenses**  
- Search for **Dominique Koch**  
- Select **Assign**  
- Verify license under:  
  **Entra ID → Users → Dominique → Licenses**

---

## 🏢 Real-World Scenarios & Practical Notes

### Scenario 1: New Starter Needs Immediate Access Before Group-Based Licensing Is Ready
Sometimes HR creates a user late, or the user needs urgent access before group membership syncs.

**Fix:**
- Assign license directly  
- Add user to correct groups later  
- Remove direct license once group-based licensing takes over  

**Why this happens:**  
Group membership sync (especially hybrid) can take minutes to hours.

---

### Scenario 2: User Missing Access Because Usage Location Was Not Set
As the document states:  
> “Before you can assign a license to a user, you must specify the Usage location property.”

**Symptoms:**
- License assignment fails  
- User cannot access Teams, Exchange, SharePoint  

**Fix:**
- Set usage location under **User → Profile**  
- Reassign license  

---

### Scenario 3: User Has Conflicting Service Plans
Example from the document:  
> “SharePoint Online (Plan 2) conflicts with SharePoint Online (Plan 1).”

**Fix:**
- Disable conflicting plans  
- Remove old license SKU  
- Standardize licensing model  

---

### Scenario 4: User Assigned License but Still Cannot Access Apps
**Common causes:**
- Service plans disabled  
- Replication delay  
- Conditional Access blocking access  
- User signed in before license activation  

**Fix:**
- Check **User → Licenses → Apps**  
- Use **What If** tool for CA  
- Ask user to sign out/in  
- Check sign-in logs  

---

## 🛠 Common IT Tickets You’ll See in This Area

| Ticket Type | Description | Typical Fix |
|------------|-------------|-------------|
| **“Please assign a license to this user”** | New starter | Assign license directly or via group |
| **“User cannot access Outlook/Teams”** | Missing service plan | Enable service plan or assign correct SKU |
| **“Usage location error”** | Location not set | Set usage location + reassign |
| **“User has conflicting licenses”** | Overlapping SKUs | Disable conflicting plans |
| **“User still unlicensed after assignment”** | Processing delay | Reprocess user or check errors |

---

## 🧩 Troubleshooting Patterns

- **Check usage location first** — most license failures start here.  
- **Review license assignment errors** under the user object.  
- **Avoid mixing direct + group licenses** unless necessary.  
- **Check service plan toggles** when users report missing app access.  
- **Use audit logs** to track who assigned or removed licenses.  

---

## 📌 Key Takeaways
- Direct license assignment is useful for exceptions, urgent access, and one-off users.  
- Usage location is mandatory for correct license assignment.  
- Service plan conflicts and insufficient seats are common blockers.  
- Always verify license assignment in both portals (Entra + M365 Admin Center).  
- Group-based licensing should be the long-term strategy, but direct assignment still has its place.

