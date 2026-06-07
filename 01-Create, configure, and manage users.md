## Create, Configure, and Manage Users

### 📘 Summary
Every user who needs access to corporate resources requires a Microsoft Entra ID account. A user object stores identity attributes used for authentication and authorization. Once authenticated, Entra issues an access token that determines what the user can access and what actions they can perform.

User accounts fall into three main categories:
- **Cloud identities** – created and managed directly in Entra ID.
- **Directory-synchronized identities** – sourced from on-prem AD via Cloud Sync or Entra Connect Sync.
- **Guest identities** – external users invited via B2B collaboration.

Admins typically manage users through:
- **Microsoft Entra admin center**
- **PowerShell / Graph API**
- **Automation workflows** (HR-driven provisioning, SCIM, Logic Apps)

---

### 🏢 Real-World Scenarios & Practical Notes

#### **Scenario 1: New Starter Provisioning**
A new employee joins the company and needs:
- A user account  
- Licenses (M365, Entra ID P1/P2, Intune, etc.)  
- Group memberships  
- Role assignments  
- Conditional Access applicability  

**Common issues:**
- HR system didn’t sync → user not created  
- User created but missing licenses → can’t sign in  
- User created but not added to correct groups → missing app access  
- User created in wrong OU (for hybrid orgs) → sync fails  

**Solution approach:**
- Validate user exists in Entra ID  
- Check **Source** attribute (Cloud / Windows Server AD / Invited)  
- Confirm group-based licensing is applied  
- Review provisioning logs (if using HR-driven provisioning)  
- Check Entra Connect Sync logs for hybrid identities  

---

#### **Scenario 2: User Cannot Sign In**
A user reports they cannot log in to Outlook, Teams, or any M365 service.

**Possible causes:**
- Account disabled  
- Password expired (for hybrid users)  
- Conditional Access blocking sign-in  
- MFA registration issues  
- Incorrect UPN suffix (hybrid mismatch)  

**Troubleshooting steps:**
- Check **Sign-in logs** in Entra ID  
- Validate user status (enabled/disabled)  
- Confirm authentication methods  
- Review Conditional Access “What If” tool  
- For hybrid users: check AD password + sync health  

---

#### **Scenario 3: Duplicate or Incorrect User Attributes**
A user appears twice in Entra ID or has incorrect details (name, department, manager).

**Root causes:**
- Duplicate AD objects  
- Incorrect HR data  
- Sync rules misconfigured  
- Manual edits conflicting with authoritative source  

**Fix:**
- Identify authoritative system (HR → AD → Entra)  
- Correct attributes at the source  
- Force sync (Cloud Sync or Connect Sync)  
- Avoid editing synced attributes directly in Entra  

---

#### **Scenario 4: Guest User Access Issues**
A vendor or contractor cannot access shared resources.

**Common causes:**
- Invitation not accepted  
- Guest blocked by Conditional Access  
- Guest missing group membership  
- External collaboration settings restricted  

**Resolution:**
- Resend invitation  
- Check B2B collaboration settings  
- Validate guest’s home tenant MFA requirements  
- Add guest to correct groups or app roles  

---

### 🛠 Common IT Tickets You’ll See in This Area

| Ticket Type | Description | Typical Fix |
|------------|-------------|-------------|
| **“Please create a new user”** | HR requests new starter setup | Create user → assign license → add to groups |
| **“User cannot sign in”** | Authentication failure | Check sign-in logs → password reset → CA review |
| **“User missing access to X app”** | Group or role misalignment | Add to correct group or app role |
| **“Guest user cannot access shared file”** | B2B or CA issue | Reinvite → adjust CA → verify guest identity |
| **“User details incorrect”** | Name/department mismatch | Update AD/HR → sync → verify attributes |
| **“Account disabled unexpectedly”** | Security or automation action | Review audit logs → re-enable if appropriate |

---

### 🧩 Troubleshooting Patterns

- **Always start with sign-in logs** → they reveal 90% of issues.  
- **Check the user’s “Source”** → determines what you can edit.  
- **Group-based licensing > manual licensing** → reduces human error.  
- **Use Access Reviews** for guest lifecycle management.  
- **Automate provisioning** where possible (HR → Entra).  

---

### 📌 Useful Admin Commands (PowerShell / Graph)

#### **Check user details**
```powershell
Get-MgUser -UserId user@domain.com

#### **List user group membershipss**
Get-MgUserMemberOf -UserId user@domain.com

#### **Create a cloud-only user**
New-MgUser -DisplayName "John Doe" -UserPrincipalName "john.doe@domain.com" `
-PasswordProfile @{ Password = "TempP@ssw0rd!" } -AccountEnabled $true



#### **🧠 Key Takeaways**
🧠 Key Takeaways
- Know the difference between cloud, synced, and guest identities.
- Understand where each attribute is sourced from.
- Use logs and automation to reduce repetitive admin work.
- Expect a mix of access issues, provisioning issues, and identity lifecycle problems in real workplaces.

