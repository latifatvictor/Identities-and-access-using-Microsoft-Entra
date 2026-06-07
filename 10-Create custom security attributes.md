## Custom Security Attributes in Microsoft Entra ID

### 📘 Summary
Custom security attributes are **business-specific key–value pairs** that you define and assign to Microsoft Entra objects.  
They allow organizations to extend identity data, categorize objects, and enforce fine‑grained access control.

As the documentation states:  
> “Custom security attributes in Microsoft Entra ID are business-specific attributes (key-value pairs) that you can define and assign to Microsoft Entra objects.”

These attributes support:
- Users  
- Enterprise applications (service principals)  
- Directory-synced users  

They are **not** supported in:
- Microsoft Entra Domain Services  
- SAML token claims  
- JWT token claims  

---

## 🏢 Why Use Custom Security Attributes?

### 1. Extend User Profiles
Example: Add **HourlySalary**, **EmployeeType**, **ClearanceLevel**, or **ProjectCode**.

### 2. Restrict Visibility
> “Ensure only administrators can see the Hourly Salary attribute…”

Attributes can be locked down so only specific roles can view or modify them.

### 3. Categorize Applications
Useful for:
- Auditing  
- Inventory management  
- Governance  
- Delegated administration  

### 4. Fine-Grained Access Control
Example:  
Grant access to Azure Storage blobs only to users with attribute:  
`Project = Alpha`  

This enables attribute-based access control (ABAC).

---

## 🧩 Features of Custom Security Attributes

- Available **tenant-wide**  
- Support **Boolean**, **Integer**, **String**  
- Support **single or multiple values**  
- Support **free-form or predefined values**  
- Can be assigned to **directory-synced users**  
- Include optional **descriptions**  
- Support **attribute governance** (who can assign what)

---

## 🏢 Real-World Scenarios & Practical Notes

### Scenario 1: Attribute-Based Access Control (ABAC)
A company wants only employees assigned to **Project Phoenix** to access a specific Azure Storage container.

**Solution:**
- Create attribute: `Project = Phoenix`  
- Assign to users  
- Configure Azure RBAC condition:  
  “Allow access if user.Project == Phoenix”

**Outcome:**  
Zero Trust, attribute-driven access.

---

### Scenario 2: Sensitive HR Data (Restricted Visibility)
HR wants to store **HourlySalary** or **EmploymentType** in Entra ID, but only HR admins should see it.

**Solution:**
- Create attribute set: `HR-Attributes`  
- Add attribute: `HourlySalary` (Integer)  
- Restrict read/write to HR admin roles  

**Outcome:**  
Secure, governed identity data.

---

### Scenario 3: Application Inventory Tagging
An enterprise with 2,000+ apps wants to categorize them by:
- Business unit  
- Data classification  
- Owner  
- Environment (Prod/Test/Dev)

**Solution:**
- Create attributes like `Environment = Production`  
- Filter apps in Entra ID using attribute queries  

**Outcome:**  
Better governance and auditability.

---

### Scenario 4: Delegated Administration
A global organization wants regional IT teams to manage only their region’s users.

**Solution:**
- Attribute: `Region = EMEA`  
- Use attribute filters in access policies  

**Outcome:**  
Scoped, least‑privilege administration.

---

## 🛠 Common IT Tickets You’ll See in This Area

| Ticket Type | Description | Typical Fix |
|------------|-------------|-------------|
| **“Add this user to Project X”** | Attribute-based access | Update custom attribute |
| **“Why can’t I see this attribute?”** | Restricted visibility | Check attribute governance |
| **“App not showing in audit filters”** | Missing attribute | Assign correct attribute |
| **“User not getting ABAC access”** | Attribute mismatch | Validate attribute values |
| **“Attribute not syncing from AD”** | Directory sync issue | Check AD schema + sync rules |

---

## 🧩 Troubleshooting Patterns

- **Check attribute set permissions** — visibility is restricted by design.  
- **Validate attribute values** — ABAC is case-sensitive.  
- **Ensure usage of predefined values** when required.  
- **Check directory sync rules** for synced users.  
- **Use audit logs** to track attribute changes.  

---

## 🧪 What You Can Do with Custom Security Attributes

- Define business-specific metadata  
- Assign attributes to users and service principals  
- Query/filter objects using attributes  
- Enforce ABAC in Azure  
- Govern attribute visibility and modification  
- Support directory-synced users  

---

## 📌 Key Takeaways
- Custom security attributes extend Entra ID beyond standard identity fields.  
- They support ABAC, governance, and large-scale object categorization.  
- They are tenant-wide, flexible, and secure.  
- They are not available in token claims (SAML/JWT).  
- They enable powerful, fine-grained access control scenarios.

