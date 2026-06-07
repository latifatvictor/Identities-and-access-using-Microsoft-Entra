## Microsoft Entra Roles & Role-Based Access Control (RBAC)

### 📘 Summary
Microsoft Entra roles define **who can do what** inside Microsoft Entra ID.  
They control permissions for managing identity resources such as users, groups, applications, devices, billing, and security settings.

Managing access using roles is known as **role-based access control (RBAC)**.  
Microsoft Entra supports:
- **Built‑in roles** (predefined, fixed permissions)  
- **Custom roles** (admin-defined permissions and scopes)

This is referred to as **Microsoft Entra RBAC**.

---

## 🧩 Built‑In Roles

Microsoft Entra ID includes many built‑in roles with fixed permissions.  
Some of the most common:

### **Global Administrator**
- Full access to all administrative features  
- First user who creates the tenant becomes Global Admin  
- Should be assigned sparingly  

### **User Administrator**
- Create, update, delete users  
- Manage groups  
- Reset passwords  
- Manage support tickets and service health  

### **Billing Administrator**
- Manage subscriptions  
- Make purchases  
- View invoices  
- Manage support tickets  

Built‑in roles are **preconfigured bundles** of permissions and **cannot be modified**.

---

## 🛠 Custom Roles

Custom roles provide flexibility when built‑in roles are too broad.

### How Custom Roles Work
1. **Create a role definition**  
   - Choose permissions from a preset list (same permissions used by built‑in roles)

2. **Assign the role**  
   - Assign to users or groups  
   - Choose a **scope**:
     - **Organization-wide** (tenant-level)  
     - **Object-level** (e.g., a single app)  

Example:  
- Assign a custom “App Reader” role to one user for *all* apps  
- Assign the same role to another user for *only* the “Contoso Expense Reports” app  

### Licensing
Custom roles require **Microsoft Entra ID P1 or P2**.

---

## 🔐 Principle of Least Privilege

Best practice:  
> “Only grant the access users need.”

Assigning least privilege:
- Reduces blast radius of compromised accounts  
- Limits what AI workloads can access when operating under delegated permissions  
- Prevents accidental or malicious configuration changes  

Example:  
If someone manages users, assign **User Administrator**, not **Global Administrator**.

---

## 🏢 Categories of Microsoft Entra Roles

Microsoft Entra roles fall into three broad categories:

### 1. **Microsoft Entra–Specific Roles**
Manage Entra-only resources:
- User Administrator  
- Groups Administrator  
- Application Administrator  

### 2. **Service-Specific Roles**
Manage individual Microsoft 365 services:
- Exchange Administrator  
- SharePoint Administrator  
- Teams Administrator  
- Intune Administrator  

These services have their own RBAC systems, but Entra provides entry-point roles.

### 3. **Cross-Service Roles**
Span multiple Microsoft 365 services:
- Security Administrator  
- Compliance Administrator  

These roles manage settings across Purview, Defender, Exchange, and more.

---

## 🆚 Microsoft Entra RBAC vs Azure RBAC

| Feature | Microsoft Entra RBAC | Azure RBAC |
|--------|------------------------|-------------|
| Controls access to | Entra resources (users, groups, apps) | Azure resources (VMs, storage, networks) |
| Used in | Microsoft Entra ID | Azure Resource Manager |
| Role definitions stored in | Entra directory | Azure Resource Manager |
| Examples | User Administrator, App Administrator | Owner, Contributor, Reader |

Both use RBAC principles, but they govern **different resource types**.

---

## 🏢 Real‑World Scenarios & Practical Notes

### Scenario 1: Overprivileged Admins Causing Security Risk
A company has 12 Global Administrators — far too many.

**Fix:**  
- Reduce to 2–4  
- Assign least-privilege roles (User Admin, App Admin, Security Admin)

---

### Scenario 2: Developer Needs Access to One App Only
A developer needs to manage a single enterprise application.

**Solution:**  
Create a **custom role** scoped to that app.

---

### Scenario 3: Helpdesk Needs Password Reset Permissions
Helpdesk staff should reset passwords but not modify groups or apps.

**Solution:**  
Assign **Helpdesk Administrator** or **Authentication Administrator**.

---

### Scenario 4: AI Workloads Need Limited Permissions
AI agents (workload identities) should only access specific resources.

**Solution:**  
Assign **custom roles** with minimal permissions.

---

## 🛠 Common IT Tickets You’ll See in This Area

| Ticket | Description | Typical Fix |
|--------|-------------|-------------|
| “User needs admin access” | Overprivileged request | Assign least-privilege role |
| “Helpdesk can’t reset password” | Missing role | Assign Authentication Administrator |
| “Developer needs app access” | Scope issue | Assign role at app scope |
| “Admin can’t access Teams settings” | Wrong role | Assign Teams Administrator |
| “Security team needs read-only access” | Audit requirement | Assign Security Reader |

---

## 🧩 Troubleshooting Patterns

- Check **role assignments** at both tenant and object scope  
- Use **Access Reviews** to clean up stale admin roles  
- Use **Privileged Identity Management (PIM)** for just‑in‑time admin access  
- Review **audit logs** for role assignment changes  
- Avoid assigning Global Admin unless absolutely necessary  

---

## 📌 Key Takeaways
- Microsoft Entra RBAC controls access to identity resources  
- Built‑in roles are fixed; custom roles provide flexibility  
- Always apply the **principle of least privilege**  
- Roles can be scoped to the entire tenant or a single object  
- Entra RBAC and Azure RBAC serve different purposes  
- Proper role governance reduces risk from both human and AI-driven threats  

