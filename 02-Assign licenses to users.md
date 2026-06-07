## Exercise – Assign Licenses to Users

### 📘 Summary
This exercise covers:
- Creating a new cloud-only user  
- Creating a security group  
- Assigning licenses to a group (group-based licensing)  
- Understanding user deletion and restoration  

These are foundational identity lifecycle tasks every Identity & Access Administrator performs regularly.

---

## 🏢 Real-World Scenarios & Practical Notes

### Scenario 1: New User Created but Not Receiving Licenses
You create a user (e.g., Chris Green), add them to a group, but the user still shows **“Unlicensed”**.

**Common causes:**
- Group-based licensing not enabled or misconfigured  
- License SKU has no available seats  
- User added to group before license assignment completed  
- License assignment errors (e.g., conflicting service plans)  

**Fix:**
- Check **Billing → Licenses → (SKU) → Assignments**  
- Confirm the group is listed under “Licensed groups”  
- Review **Azure portal → Users → Chris Green → Licenses → Errors**  
- If needed, remove and re-add the user to the group  

---

### Scenario 2: User Cannot Access Apps Even Though License Assigned
User says: *“I have a license but I still can’t access Outlook/Teams/SharePoint.”*

**Possible causes:**
- License assigned but service plans disabled  
- Conditional Access blocking access  
- Replication delay (usually < 15 minutes)  
- User signed in before license activation  

**Fix:**
- Check **User → Licenses → Apps** to ensure service plans are ON  
- Use the **What If** tool to test Conditional Access  
- Ask user to sign out and sign back in  
- Validate sign-in logs for errors  

---

### Scenario 3: Group-Based Licensing Not Applying to All Members
You assign a license to the **Marketing** group, but only some members receive it.

**Root causes:**
- Dynamic group rules (if used) still processing  
- User has conflicting license assignments  
- License SKU exhausted  
- User object is in a “pending” state (common in hybrid sync)  

**Fix:**
- Check **Group → Licensing → Errors**  
- Ensure SKU has available seats  
- For hybrid users: confirm AD sync health  
- Reprocess group membership  

---

### Scenario 4: Guest Users Accidentally Assigned Licenses
A contractor or vendor is added to a group that has licenses assigned.

**Impact:**
- Consumes paid licenses  
- Violates licensing compliance  
- Guest may not need full M365 access  

**Fix:**
- Remove guest from licensed groups  
- Revoke license under **User → Licenses**  
- Review group membership policies  
- Use Access Reviews to clean up external users  

---

## 🛠 Common IT Tickets You’ll See in This Area

| Ticket Type | Description | Typical Fix |
|------------|-------------|-------------|
| **“Please assign a license to this user”** | New starter or role change | Add user to licensed group |
| **“User has no mailbox”** | License missing Exchange Online | Enable service plan or assign correct SKU |
| **“Teams not working”** | Missing Teams service plan | Check service plan toggles |
| **“Guest user consuming license”** | Guest added to licensed group | Remove guest + adjust group membership |
| **“User still unlicensed after group assignment”** | Licensing delay or error | Check group licensing errors |

---

## 🧩 Troubleshooting Patterns

- **Always check group-based licensing first** before assigning licenses manually.  
- **Avoid direct license assignment** unless necessary — groups reduce human error.  
- **Check service plan toggles** when users report missing app access.  
- **Use audit logs** to track who assigned or removed licenses.  
- **Monitor license consumption** to avoid SKU exhaustion.  

---

## 🧪 Lab Steps (Condensed for Notes)

### 1. Create a New User
- Go to **Identity → Users → All Users → New User**  
- Create user:  
  - UPN: `ChrisG`  
  - Name: Chris Green  
  - Password: unique temporary password  
- Verify user appears in the directory  

### 2. Create a Security Group
- Go to **Identity → Groups → All Groups → New Group**  
- Group type: Security  
- Name: Marketing  
- Membership: Assigned  
- Add **Chris Green** as a member  
- Add yourself as owner  

### 3. Assign License to Group
- Go to **Microsoft 365 Admin Center → Billing → Licenses**  
- Select a license SKU  
- Select **Groups** → **Assign license**  
- Choose **Marketing** group  
- Confirm assignment  

### 4. Restore or Permanently Delete Users
- Deleted users remain recoverable for **30 days**  
- Roles required:  
  - Global Admin  
  - User Admin  
  - Partner Tier 1/2 Support  
- You can:  
  - Restore user  
  - Permanently delete user  
  - View deleted users list  

---

## 📌 Key Takeaways
- Group-based licensing is the recommended approach for scalable identity management.  
- Always validate license availability before assigning.  
- Deleted users can be restored within 30 days — after that, recovery is impossible.  
- License issues often manifest as app access issues, not just “unlicensed” status.  
- Proper group structure reduces repetitive admin work and IT tickets.  

