## Create, Configure, and Manage Groups

### 📘 Summary
Microsoft Entra groups help you organise users and manage access at scale. Instead of assigning permissions individually, you assign them to a group — and all members inherit those permissions automatically.

Entra supports two main group types:
- **Security Groups** — used for access control (apps, policies, resources).
- **Microsoft 365 Groups** — used for collaboration (shared mailbox, SharePoint site, Planner, Teams).

Membership types:
- **Assigned** — manually add/remove members.
- **Dynamic User** — membership based on user attributes (department, job title, location).
- **Dynamic Device** — membership based on device attributes (security groups only).

Dynamic membership requires **Entra ID P1**.

---

## 🏢 Real-World Scenarios & Practical Notes

### Scenario 1: Access Request for a New Application
A user needs access to a new SaaS app or internal system.

**Typical workflow:**
- Identify the correct security group for the app.
- Add the user to the group.
- Access propagates automatically.

**Common issues:**
- User added to wrong group.
- Group not assigned to the app.
- Group-based licensing not configured.
- Dynamic group rules not matching user attributes.

**Fix:**
- Validate group-to-app assignment.
- Check user attributes if dynamic membership is used.
- Review audit logs to confirm membership changes.

---

### Scenario 2: Department Change Not Reflected in Access
A user moves from **Marketing** to **Finance**, but still has access to Marketing resources.

**Root causes:**
- Dynamic group rules not configured.
- User attributes not updated in HR/AD.
- Manual groups used instead of dynamic groups.

**Fix:**
- Update user attributes at the authoritative source (HR or AD).
- Use dynamic groups for department-based access.
- Review group membership history.

---

### Scenario 3: Too Many Groups, No Naming Convention
Large organisations often end up with:
- Duplicate groups  
- Unclear group purpose  
- Groups with no owners  
- Groups with no members  

**Impact:**
- Security risk  
- License waste  
- Hard-to-manage access  

**Fix:**
- Implement naming conventions (e.g., `SG-App-SharePoint-Read`).
- Use Access Reviews to clean up stale groups.
- Assign group owners.
- Document group purpose in the description field.

---

### Scenario 4: Dynamic Group Not Updating Membership
A user should be added automatically to a dynamic group but isn’t.

**Common causes:**
- Rule syntax incorrect.
- Attribute mismatch (e.g., “Marketing” vs “marketing”).
- Attribute not synced from on-prem AD.
- User recently updated — rule evaluation pending.

**Fix:**
- Validate rule using the **Rule Validation** tool.
- Check user attributes in Entra.
- Confirm sync health for hybrid environments.
- Wait for rule re-evaluation (usually < 5 minutes).

---

## 🛠 Common IT Tickets You’ll See in This Area

| Ticket Type | Description | Typical Fix |
|------------|-------------|-------------|
| **“Please add/remove this user from a group”** | Access request | Add/remove user from security group |
| **“User changed department but still has old access”** | Attribute mismatch | Update attributes → dynamic group re-evaluates |
| **“Group has no owner”** | Governance issue | Assign owner(s) |
| **“Group not applying permissions”** | Misconfigured group-to-resource mapping | Validate app/resource assignment |
| **“Dynamic group not working”** | Rule or attribute issue | Validate rule + check user attributes |

---

## 🧩 Troubleshooting Patterns

- **Check group type** — Security vs Microsoft 365 affects behaviour.  
- **Check membership type** — Assigned vs Dynamic determines how to fix issues.  
- **Use audit logs** to see who added/removed members.  
- **Validate dynamic rules** using the built-in rule tester.  
- **Avoid manual membership** for large or frequently changing departments.  
- **Use naming conventions** to avoid confusion and duplication.

---

## 🧪 Lab Notes (Condensed)

### 1. View Groups
- Go to **Identity → Groups → All Groups**  
- Review existing groups and membership types  

### 2. Create a Security Group
- Group type: Security  
- Membership: Assigned  
- Add members manually  

### 3. Create a Dynamic Group (Example)
Rule example for Marketing department: (user.department -eq "Marketing")


### 4. Validate Dynamic Membership
- Use **Dynamic membership rule validation**  
- Check user attributes  
- Confirm rule syntax  

---

## 📌 Key Takeaways
- Groups simplify access management and reduce admin overhead.  
- Dynamic groups are essential for scalable, attribute-driven access.  
- Always check group type and membership type before troubleshooting.  
- Naming conventions and governance prevent long-term access chaos.  
- Group-based access is the foundation of Zero Trust and least privilege.




