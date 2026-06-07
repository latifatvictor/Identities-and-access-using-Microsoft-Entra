## Remove and Restore Users in Microsoft Entra ID

### 📘 Summary
This section covers:
- Deleting users from Microsoft Entra ID  
- Understanding soft-delete (30‑day retention)  
- Restoring deleted users  
- Permanently deleting users  

When a user is deleted, the account enters a **soft-deleted** state for 30 days. During this period, the user can be restored with all attributes intact. After 30 days, the deletion becomes permanent and **cannot** be reversed.

---

## 🏢 Real-World Scenarios & Practical Notes

### Scenario 1: Employee Leaves the Organisation (Offboarding)
A user leaves the company and HR raises a ticket to disable or delete the account.

**Typical steps in real environments:**
- Disable the account immediately  
- Revoke sessions  
- Remove licenses  
- Block sign-in  
- Move user to a “Disabled Users” OU (hybrid)  
- After X days (policy-based), delete the account  

**Common issues:**
- User still appears in Teams/Outlook due to caching  
- Licenses not removed → still consuming paid seats  
- Guest accounts not cleaned up  
- Shared mailbox delegation lost if user was a member  

**Fix:**
- Follow offboarding SOP  
- Use Access Reviews for guest lifecycle  
- Remove licenses before deletion  
- Document group memberships before deletion  

---

### Scenario 2: User Deleted Accidentally
An admin mistakenly deletes a user (e.g., Chris Green) while bulk‑selecting users.

**Impact:**
- User cannot sign in  
- Mailbox becomes inaccessible  
- Assigned apps stop working  
- Conditional Access assignments break  

**Fix:**
- Go to **Users → Deleted Users**  
- Select the user → **Restore**  
- Reassign licenses if not automatically restored  
- Validate group memberships (sometimes not restored in hybrid setups)  

---

### Scenario 3: Hybrid User Deleted On-Premises
A synced user is deleted in on-prem AD, which triggers deletion in Entra ID.

**Common issues:**
- Admin tries to restore the user in Entra ID → fails  
- User keeps reappearing as deleted after restore  
- Mailbox becomes orphaned  

**Fix:**
- Restore the user **on-premises**, not in Entra  
- Force sync (Cloud Sync or Connect Sync)  
- Reconnect mailbox if needed  

---

### Scenario 4: Guest User Needs to Be Removed
A contractor finishes a project and must be removed.

**Challenges:**
- Guest may still have access to Teams, SharePoint, or apps  
- Guest may be part of multiple groups  
- Guest may still appear in Teams chats  

**Fix:**
- Remove guest from groups  
- Delete guest account  
- Use Access Reviews to automate guest cleanup  

---

## 🛠 Common IT Tickets You’ll See in This Area

| Ticket Type | Description | Typical Fix |
|------------|-------------|-------------|
| **“Please disable and delete this user”** | Offboarding request | Disable → remove licenses → delete |
| **“User was deleted by mistake”** | Accidental deletion | Restore from Deleted Users |
| **“Guest still has access after project ended”** | Guest lifecycle issue | Remove from groups → delete guest |
| **“Mailbox missing after restore”** | Hybrid identity issue | Restore on-prem AD object |
| **“User still appears in Teams after deletion”** | Cached presence | Teams cache clears automatically |

---

## 🧩 Troubleshooting Patterns

- **Check Deleted Users first** before assuming a user is permanently gone.  
- **Hybrid users must be restored on-prem**, not in Entra.  
- **Licenses may not automatically reassign** after restore — verify manually.  
- **Audit logs** show who deleted the user and when.  
- **Soft-delete applies to users, groups, and some resources**, but not all.  

---

## 🧪 Lab Steps (Condensed for Notes)

### 1. Remove a User
- Go to **Identity → Users → All Users**  
- Select the checkbox next to the user (e.g., Chris Green)  
- Select **Delete user**  
- Confirm deletion  

### 2. Restore a Deleted User
- Go to **Identity → Users → Deleted Users**  
- Select the user  
- Choose **Restore user**  
- Confirm restoration  
- Go back to **All Users** to verify the user is active  

---

## 📌 Key Takeaways
- Deleted users remain recoverable for 30 days — after that, recovery is impossible.  
- Always check whether the user is cloud-only, synced, or guest before restoring.  
- Accidental deletions are common in bulk operations — audit logs help identify the cause.  
- Restoring a user may require reassigning licenses or re-adding group memberships.  
- Offboarding processes should be standardised to avoid security gaps.  

