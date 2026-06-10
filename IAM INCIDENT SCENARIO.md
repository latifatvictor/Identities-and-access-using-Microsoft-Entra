# 🚨 IAM Incident Simulation – Compromised User Account

## 📌 Scenario
A user account (Bhogeswar Kalita) has been compromised due to a phishing attack.  
An attacker is attempting to access company resources from an unusual location.

---

## 🔍 Detection (How it was identified)

Step 1 > Review Sign-in logs  
Step 2 > Detect unfamiliar location (impossible travel)  
Step 3 > Observe multiple failed login attempts  
Step 4 > Detect successful login after failures  
Step 5 > Identify risky sign-in flagged by Entra  

✅ Insight:
Classic credential compromise pattern

---

## ⚠️ Impact

- Unauthorized access to applications  
- Potential data exposure  
- Risk of privilege escalation  

---

## 🛑 Immediate Response (Containment)

Step 1 > Disable user account  
Step 2 > Revoke active sessions  
Step 3 > Reset password  
Step 4 > Force MFA re-registration  

✅ Goal:
Stop attacker access immediately  

---

## 🔐 Investigation

Step 1 > Review audit logs  
Step 2 > Check accessed applications  
Step 3 > Identify any data changes  
Step 4 > Check role assignments  
Step 5 > Look for lateral movement  

✅ Goal:
Understand scope of breach  

---

## 🛡 Remediation

Step 1 > Enforce MFA for user  
Step 2 > Add Conditional Access policy  
Step 3 > Block risky sign-ins  
Step 4 > Remove unnecessary roles  
Step 5 > Educate user (phishing awareness)  

✅ Goal:
Prevent recurrence  

---

## 🔁 Prevention Improvements

- Enable MFA for all users  
- Use Conditional Access (risk-based policies)  
- Enable Identity Protection alerts  
- Implement password protection policies  
- Use SSPR + strong authentication methods  

---

## 🧠 Lessons Learned

- Identity = primary attack surface  
- MFA could have prevented this  
- Monitoring = critical for early detection  
- Response time reduces impact  

---

## ✅ Final Summary

Detect > Contain > Investigate > Remediate > Prevent
``
