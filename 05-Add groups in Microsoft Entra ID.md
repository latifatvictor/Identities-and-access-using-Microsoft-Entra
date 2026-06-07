## Create a Microsoft 365 Group in Microsoft Entra ID

### 📘 Summary
Microsoft 365 Groups are collaboration-focused groups that provide:
- A shared mailbox  
- A shared calendar  
- A SharePoint site  
- A Planner workspace  
- Optional Teams integration  

They differ from Security Groups because they are designed for **collaboration**, not just access control.  
Microsoft 365 Groups can include internal users and external guests (if allowed by policy).

In this exercise, you create:
- **Group type:** Microsoft 365  
- **Group name:** Northwest Sales  
- **Membership type:** Assigned  
- **Owner:** Your admin account  
- **Members:** Any user you choose  

After creation, the group may take a few seconds to appear — refreshing the page helps.

---

## 🏢 Real-World Scenarios & Practical Notes

### Scenario 1: New Team or Department Needs Collaboration Space
A new regional sales team (e.g., Northwest Sales) is formed and needs:
- A shared mailbox for customer enquiries  
- A shared calendar for team meetings  
- A SharePoint site for documents  
- A Planner board for tasks  
- A Teams workspace  

**Fix / Best Practice:**
- Create a Microsoft 365 Group  
- Add members  
- Enable Teams if required  
- Apply naming conventions (e.g., `M365-NW-Sales`)  
- Assign at least two owners to avoid orphaned groups  

---

### Scenario 2: Group Not Appearing in Outlook or Teams
A newly created Microsoft 365 Group doesn’t show up in Outlook or Teams.

**Common causes:**
- Group creation still propagating  
- HiddenFromExchangeClientsEnabled set to True  
- Teams not enabled for the group  
- Licensing issues  

**Fix:**
- Wait 5–10 minutes for propagation  
- Check group settings in Entra and Exchange Online  
- Enable Teams via the Teams admin center  
- Ensure members have appropriate licenses  

---

### Scenario 3: External Guests Cannot Access Group Resources
A Microsoft 365 Group is created for a project involving external partners, but guests cannot access files or the shared mailbox.

**Root causes:**
- External collaboration disabled at tenant level  
- SharePoint external sharing disabled  
- Guest access disabled in Teams  
- Group privacy set to Private  

**Fix:**
- Check **External collaboration settings** in Entra  
- Validate SharePoint sharing policies  
- Enable guest access in Teams  
- Add guests to the group manually  

---

### Scenario 4: Group Has No Owner (Orphaned Group)
A group owner leaves the company, and no one can manage the group.

**Impact:**
- No one can add/remove members  
- No one can manage the SharePoint site  
- No one can approve guest access  

**Fix:**
- Use Entra ID to assign a new owner  
- Implement governance to ensure all groups have at least two owners  
- Use Access Reviews to identify ownerless groups  

---

## 🛠 Common IT Tickets You’ll See in This Area

| Ticket Type | Description | Typical Fix |
|------------|-------------|-------------|
| **“Create a new team for our department”** | Collaboration request | Create M365 group → enable Teams |
| **“Add/remove members from our shared mailbox group”** | Membership change | Update group membership |
| **“External partner cannot access shared files”** | Guest access issue | Check external sharing + add guest |
| **“Group not showing in Outlook”** | Propagation or settings issue | Validate Exchange settings |
| **“Group has no owner”** | Governance issue | Assign new owner(s) |

---

## 🧩 Troubleshooting Patterns

- **Check group type** — Microsoft 365 vs Security determines capabilities.  
- **Check privacy settings** — Private groups restrict visibility.  
- **Check licensing** — Members need M365 licenses for mailbox/Teams.  
- **Check external sharing** — Guests require tenant-level permissions.  
- **Use audit logs** to track membership and ownership changes.  

---

## 🧪 Lab Notes (Condensed)

### 1. Create a Microsoft 365 Group
- Go to **Identity → Groups → All Groups → New Group**  
- Group type: **Microsoft 365**  
- Group name: **Northwest Sales**  
- Membership type: **Assigned**  
- Add yourself as **Owner**  
- Add a user as **Member**  

### 2. Verify Group Creation
- Return to **All Groups**  
- Refresh the page a few times  
- Confirm **Northwest Sales** appears  

---

## 📌 Key Takeaways
- Microsoft 365 Groups are collaboration-first and integrate deeply with Outlook, SharePoint, Planner, and Teams.  
- Always assign at least two owners to avoid orphaned groups.  
- External access depends on tenant-wide collaboration settings.  
- Group creation may take time to propagate across services.  
- Use naming conventions and governance to avoid group sprawl.

