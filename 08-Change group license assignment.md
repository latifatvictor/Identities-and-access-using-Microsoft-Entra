## Change Group License Assignments & Troubleshoot Licensing Errors

### 📘 Summary
Group-based licensing allows administrators to assign product licenses to a **security group**, and Microsoft Entra ID automatically ensures all members inherit those licenses.  
When licenses change, you update them through the **Microsoft 365 admin center**, not directly in Entra ID.  
As the document states:  
> “You find that you have to use the Microsoft 365 Admin Center to make any updates.”  
> “Group-based licensing in Microsoft Entra ID introduces the concept of users in a licensing error state.”

This section covers:
- How to change group license assignments  
- How to identify and resolve licensing errors  
- Real-world scenarios and troubleshooting patterns  
- Migration from direct licensing to group-based licensing  

---

## 🧪 How to Change Group License Assignments (Lab Notes)

### 1. Review Group Licenses in Entra ID
- Go to **Groups → All Groups → Select Group → Licenses**  
- Review current assignments  
- Select **+ Assignments** → redirected to Microsoft 365 Admin Center  

### 2. Update Licenses in Microsoft 365 Admin Center
- Go to **Billing → Licenses**  
- Select a license SKU  
- Select **Groups**  
- Choose **+ Assign licenses**  
- Select the group  
- Confirm assignment  

### 3. Verify Changes
- Check the group’s **Licenses** page in both portals  
- Ensure processing completes  

---

## 🏢 Real-World Scenarios & Practical Notes

### Scenario 1: Group License Assignment Fails (Error State)
Microsoft Entra ID processes group licenses **in the background**, so errors appear later.  
As the document states:  
> “The original intent to license the user is never lost, but it's recorded in an error state for future investigation.”

**Common causes:**
- Not enough licenses  
- Conflicting service plans  
- Usage location not allowed  
- Dependent service plans missing  
- Duplicate proxy addresses  

**Fix:**
- Review user’s **Licenses → Errors**  
- Resolve root cause  
- Reprocess group or user  

---

### Scenario 2: Not Enough Licenses
> “There aren't enough available licenses for one of the products specified in the group.”

**Fix:**
- Purchase more licenses  
- Free up unused licenses  
- Remove direct assignments from inactive users  

**PowerShell error:** `CountViolation`

---

### Scenario 3: Conflicting Service Plans
> “Some service plans are configured in a way that they can't be assigned to the same user.”

Example from the document:
- SharePoint Online Plan 2 conflicts with Plan 1  
- Exchange Online Plan 2 conflicts with Plan 1  

**Fix options:**
- Disable conflicting plans in the group  
- Remove direct license from user  
- Standardize licensing model  

**PowerShell error:** `MutuallyExclusiveViolation`

---

### Scenario 4: Dependent Service Plans Missing
> “One of the products contains a service plan that must be enabled for another service plan… to function.”

Example:
- Removing E3 may break Audio Conferencing  
- Entra converts inherited license → direct license  

**Fix:**
- Ensure prerequisite plans remain assigned  
- Disable dependent services before removal  

**PowerShell error:** `DependencyViolation`

---

### Scenario 5: Usage Location Not Allowed
> “Some Microsoft services aren't available in all locations… you must specify the Usage location property.”

**Fix:**
- Set usage location on user  
- Remove users from unsupported regions  
- Reprocess group  

**PowerShell error:** `ProhibitedInUsageLocationViolation`

---

### Scenario 6: Duplicate Proxy Addresses
> “Proxy address is already being used.”

**Fix:**
- Correct duplicate proxy addresses  
- Reprocess user  

---

### Scenario 7: LicenseAssignmentAttributeConcurrencyException
> “This typically happens when a user is a member of more than one group with same assigned license.”

**Fix:**  
- No action required — Entra retries automatically  

---

## 🛠 Common IT Tickets You’ll See in This Area

| Ticket Type | Description | Typical Fix |
|------------|-------------|-------------|
| **“User not receiving license from group”** | Error state | Check errors → fix → reprocess |
| **“We need to change E1 users to E3”** | License migration | Update group license assignment |
| **“User has conflicting service plans”** | Overlapping SKUs | Disable conflicting plans |
| **“Usage location error”** | Missing location | Set usage location |
| **“Group deletion blocked due to licenses”** | Dependent services | Remove dependencies first |

---

## 🔄 Reprocessing Groups & Users

### Reprocess a Group
> “Go to the group pane, open Licenses, and then select the Reprocess button.”

Use when:
- You freed up licenses  
- You fixed service plan conflicts  
- You resolved proxy address issues  

### Reprocess a User
> “Go to the user pane, open Licenses, and then select the Reprocess button.”

Use when:
- You corrected user attributes  
- You fixed usage location  
- You resolved proxy address duplication  

---

## 🔁 Migrating from Direct Licensing to Group-Based Licensing

The document recommends a **safe migration strategy**:
> “Avoid a situation in which migrating… results in users temporarily losing their currently assigned licenses.”

### Recommended Migration Steps
1. Keep existing automation running  
2. Create licensing groups  
3. Assign licenses to groups  
4. Verify users receive inherited licenses  
5. Check for errors  
6. Gradually remove direct licenses  

### Key Insight
> “When the same product license is assigned both directly and through a group, only one license is consumed.”

This makes migration safe and cost-neutral.

---

## 🧩 Troubleshooting Patterns

- Always check **usage location** first  
- Review **license assignment errors** on user object  
- Avoid mixing direct + group licensing unless necessary  
- Use **dynamic groups** for automated lifecycle  
- Use **audit logs** to track changes  
- Reprocess groups after fixing issues  

---

## 📌 Key Takeaways
- Group-based licensing simplifies large-scale license management  
- Errors occur in the background and must be reviewed manually  
- Usage location is critical for correct license assignment  
- Conflicting and dependent service plans are common blockers  
- Migration from direct licensing must be done carefully  
- Reprocessing groups/users is essential after fixing issues  

