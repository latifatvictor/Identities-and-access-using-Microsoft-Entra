## Microsoft Entra Access Reviews

### 📘 Summary
Microsoft Entra access reviews help organizations **regularly validate who has access to what**, ensuring that only the right people retain access to groups, applications, and privileged roles.  
They address a core identity governance challenge:

> Access tends to accumulate over time as people change roles, collaborate externally, or receive temporary permissions.

Access reviews provide a scalable, automated way to:
- Reduce excessive or outdated access  
- Meet compliance and audit requirements  
- Govern internal and external user access  
- Maintain least‑privilege access across the organization  

---

## 🧩 Why Access Reviews Matter

Modern organizations collaborate with:
- Internal employees  
- Contractors  
- Vendors  
- External guests  

Users join groups, access apps, and receive roles — but rarely lose access when they no longer need it.  
Access reviews solve this by enabling **periodic recertification** of access rights.

### Common Use Cases
- Too many users in privileged roles  
- Business‑critical apps requiring periodic justification  
- Maintaining policy exception lists  
- Ensuring group owners validate guest access  
- Recurring compliance-driven access checks  

---

## 🔍 What Access Reviews Can Do

### 1. **Review Group Membership**
Ensure users and guests still need access to:
- Microsoft 365 groups  
- Security groups  
- Teams  
- Distribution lists  

### 2. **Review App Assignments**
Validate access to enterprise applications, especially sensitive ones.

### 3. **Review Privileged Roles**
Through PIM, recertify:
- Microsoft Entra roles  
- Azure resource roles  
- Temporary or permanent admin assignments  

### 4. **Review Guest Access**
Ask group owners to confirm whether external users still need access.

### 5. **Recurring Reviews**
Schedule reviews:
- Weekly  
- Monthly  
- Quarterly  
- Annually  

Reviewers receive notifications and complete decisions through a simple UI.

---

## 🧪 How Access Reviews Work

### Reviewers Can Be:
- The user themselves (self‑attestation)  
- Group owners  
- Application owners  
- Managers  
- Privileged role administrators  
- Custom reviewers  

### Review Process
1. Reviewers receive a notification  
2. They approve or deny access  
3. Admins track progress  
4. At completion:
   - Changes can be **auto‑applied**, or  
   - Admins can **manually apply** decisions  

> No access is removed until the review is completed.

### Exceptions
- Dynamic groups  
- On‑premises–originated groups  
These require manual updates.

---

## 🔁 Multi‑Stage Access Reviews

Access reviews support **up to three sequential stages**.

Example workflow:
1. **Manager review**  
2. **App owner review**  
3. **Security team review**  

Benefits:
- Supports complex audit requirements  
- Reduces reviewer workload  
- Ensures multiple layers of oversight  

---

## 🤖 AI‑Powered Recommendations

Microsoft Entra uses AI to help reviewers make better decisions.

AI analyzes:
- Sign‑in activity  
- Group affiliation  
- Peer comparison  
- Access patterns  

AI identifies:
- **Inactive users**  
- **Users with unusual access patterns**  
- **Peer outliers** who may require extra scrutiny  

Reviewers can accept or override recommendations.

---

## 🏢 Real‑World Scenarios & Practical Notes

### Scenario 1: Privileged Role Cleanup
Too many Global Administrators exist in the tenant.

**Solution:**  
Run a PIM access review → remove unnecessary admin roles.

---

### Scenario 2: Quarterly Compliance Review for Finance Apps
Finance apps require strict access controls.

**Solution:**  
Create recurring access reviews requiring justification for continued access.

---

### Scenario 3: Guest Access Validation
Teams with external collaborators must ensure guests still need access.

**Solution:**  
Ask group owners to review guest access quarterly.

---

### Scenario 4: Maintaining Policy Exception Lists
Some users bypass Conditional Access policies for business reasons.

**Solution:**  
Review exception lists monthly to ensure they remain valid.

---

## 🛠 Common IT Tickets You’ll See in This Area

| Ticket | Description | Typical Fix |
|--------|-------------|-------------|
| “User lost access after review” | Reviewer denied access | Restore access or adjust review settings |
| “Manager didn’t complete review” | Reviewer unresponsive | Reassign reviewer or escalate |
| “Guest still has access after leaving project” | No review in place | Create recurring guest access review |
| “Too many admins” | Privileged sprawl | Run PIM access review |
| “Audit requires proof of access validation” | Compliance request | Export review results |

---

## 🧩 Troubleshooting Patterns

- Check **Access Review logs** for reviewer decisions  
- Validate **auto‑apply settings**  
- Ensure reviewers have correct permissions  
- For dynamic groups, update membership rules instead  
- For on‑prem groups, update AD directly  
- Use **PIM** for privileged role reviews  

---

## 📌 Key Takeaways
- Access reviews ensure least‑privilege access across the organization  
- They support internal users, guests, and privileged roles  
- Multi‑stage reviews support complex audit workflows  
- AI recommendations improve decision quality  
- Reviews can be recurring and automated  
- Essential for compliance, Zero Trust, and identity governance  

