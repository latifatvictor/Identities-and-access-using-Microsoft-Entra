## Automatic User Provisioning (SCIM & API-Driven Inbound Provisioning)

### 📘 Summary
Automatic user provisioning ensures that identities created or updated in an HR system (Workday, SAP SuccessFactors, custom HR apps, etc.) are automatically created, updated, or removed in Microsoft Entra ID.

As the documentation states:  
> “SCIM is an open standard protocol for automating the exchange of user identity information between identity domains and IT systems.”

Provisioning ensures:
- New hires get accounts automatically  
- Role changes update access automatically  
- Terminated users are deprovisioned immediately  
- Identity lifecycle stays accurate and secure  

This reduces manual admin work and significantly lowers security risk.

---

## 🧩 Components of SCIM Provisioning

### 1. **HCM System (Source of Truth)**
> “Applications and technologies that enable Human Capital Management… throughout the employee lifecycle.”

Examples:
- Workday  
- SAP SuccessFactors  
- Oracle HCM  
- Custom HR systems  

### 2. **Microsoft Entra Provisioning Service**
> “Uses the SCIM 2.0 protocol for automatic provisioning.”

Responsibilities:
- Connects to SCIM endpoint  
- Reads user attributes  
- Creates/updates/deletes users  
- Syncs groups and entitlements  

### 3. **Microsoft Entra ID**
> “User repository used to manage the lifecycle of identities and their entitlements.”

Stores:
- User objects  
- Group memberships  
- Access assignments  

### 4. **Target System**
> “Application or system that has SCIM endpoint…”

Examples:
- SaaS apps (Atlassian, Slack, ServiceNow)  
- Custom apps with SCIM endpoints  
- On-prem apps exposed via SCIM gateway  

---

## 🟦 Why Use SCIM?

- Automates identity lifecycle  
- Reduces manual account creation  
- Ensures immediate deprovisioning  
- Eliminates stale accounts  
- Enforces Zero Trust  
- Ensures HR is the authoritative source  

As the documentation states:  
> “If a user can be automatically deprovisioned… you have less worry about a possible breach.”

---

## 🟣 API-Driven Inbound Provisioning (2024 GA)

Not all HR systems support SCIM.  
To solve this, Microsoft introduced **API-driven inbound provisioning**.

> “Any automation tool or script can retrieve workforce data… and send it to the Microsoft Entra provisioning API.”

Supported sources:
- Workday  
- SAP SuccessFactors  
- Custom HR systems  
- Any system that can call REST APIs  

This gives organizations full flexibility.

---

## 🏢 Real-World Scenarios & Practical Notes

### Scenario 1: New Hire Appears in HR System → Automatically Created in Entra
A new employee is added to Workday.

**What happens:**
- HR enters employee details  
- Provisioning service detects new record  
- Creates user in Entra ID  
- Assigns groups, roles, licenses  
- Sends welcome email  

**Common issues:**
- Missing required attributes  
- Incorrect mapping  
- HR record incomplete  

**Fix:**
- Review attribute mappings  
- Check provisioning logs  
- Validate HR data  

---

### Scenario 2: Employee Terminated → Immediate Deprovisioning
A user leaves the company.

**What happens:**
- HR marks user as terminated  
- Provisioning service disables account  
- Removes licenses  
- Removes group memberships  
- Revokes sessions  

**Security impact:**  
Prevents orphaned accounts and reduces breach risk.

---

### Scenario 3: Role Change → Access Updated Automatically
A user moves from Sales to Finance.

**What happens:**
- HR updates job role  
- Provisioning updates user attributes  
- User removed from Sales groups  
- User added to Finance groups  
- Access changes instantly  

**Fix if issues occur:**
- Check attribute mapping rules  
- Validate dynamic group rules  
- Review provisioning logs  

---

### Scenario 4: Custom HR System Without SCIM Support
A company uses a legacy HR system.

**Solution:**  
Use **API-driven inbound provisioning**.

**Flow:**
- Script pulls HR data  
- Script pushes data to Entra provisioning API  
- Entra handles lifecycle  

**Outcome:**  
Full automation without SCIM support.

---

## 🛠 Common IT Tickets You’ll See in This Area

| Ticket Type | Description | Typical Fix |
|------------|-------------|-------------|
| **“New starter not created in Entra”** | Provisioning failure | Check logs + attribute mapping |
| **“Terminated user still active”** | HR not updated | Validate HR record + re-run provisioning |
| **“Role change not reflected in access”** | Attribute mismatch | Check mapping + dynamic groups |
| **“User created with missing attributes”** | HR data incomplete | Fix HR record + reprocess |
| **“Provisioning stuck or slow”** | Sync backlog | Review provisioning cycle logs |

---

## 🧩 Troubleshooting Patterns

- Always check **Provisioning Logs** first  
- Validate attribute mappings (source → target)  
- Ensure HR system is authoritative  
- Confirm SCIM endpoint availability  
- For API-driven provisioning, validate API payload  
- Use **Test Connection** in provisioning settings  
- Re-run provisioning cycle if needed  

---

## 📌 Key Takeaways
- SCIM automates identity lifecycle across systems  
- API-driven inbound provisioning adds flexibility for non-SCIM HR systems  
- Automatic provisioning reduces manual work and improves security  
- HR becomes the single source of truth  
- Provisioning logs are essential for troubleshooting  

