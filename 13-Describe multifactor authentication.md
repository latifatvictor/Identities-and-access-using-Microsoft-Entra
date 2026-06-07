## Multifactor Authentication (MFA) in Microsoft Entra ID

### 📘 Summary
Multifactor authentication (MFA) requires users to provide **two or more** verification factors during sign-in.  
This dramatically reduces the risk of account compromise, especially when passwords are weak, reused, or leaked.

As the documentation states:  
> “When you require a second form of authentication, security is increased because this additional factor isn't something that's easy for an attacker to obtain or duplicate.”

Microsoft Entra MFA uses combinations of:
- **Something you know** — password or PIN  
- **Something you have** — trusted device, phone, hardware key  
- **Something you are** — biometrics  

MFA prompts are automatically triggered during Microsoft Entra sign-in events. No application changes are required.

---

## 🔐 Available MFA Verification Methods

Microsoft Entra ID supports a wide range of MFA methods:

- **Microsoft Authenticator**  
- **Authenticator Lite (Outlook Mobile)**  
- **Windows Hello for Business**  
- **Passkeys (FIDO2)**  
- **Passkeys in Microsoft Authenticator**  
- **Certificate-Based Authentication (CBA)**  
- **External authentication methods** (Duo, RSA, etc.)  
- **Temporary Access Pass (TAP)**  
- **OATH hardware tokens**  
- **OATH software tokens**  
- **SMS**  
- **Voice call**

These methods support different scenarios, device types, and security requirements.

---

## 🏢 Real-World Scenarios & Practical Notes

### Scenario 1: Preventing Account Takeover
A user’s password is leaked in a phishing attack.

**Without MFA:**  
Attacker signs in immediately.

**With MFA:**  
Attacker is blocked because they cannot complete the second factor.

**Best practice:**  
Use **Authenticator push with number matching** or **passkeys**.

---

### Scenario 2: Onboarding New Users Without Passwords
A new employee joins the company but has no registered authentication methods.

**Solution:**  
Issue a **Temporary Access Pass (TAP)**.

**Outcome:**  
User signs in → registers passwordless methods → MFA ready.

---

### Scenario 3: Frontline Workers on Shared Devices
Frontline staff often share devices and cannot install apps.

**Solution:**  
Use **QR code authentication** + PIN.

---

### Scenario 4: Legacy MFA Provider Already in Use
An organization uses Duo Security for MFA.

**Solution:**  
Enable **external authentication methods** in Entra ID.

---

## 🛡️ Security Defaults & MFA

Security defaults enforce:
- MFA registration for all users  
- MFA for all admins  
- MFA when risk is detected  
- Blocking legacy authentication  
- Protecting privileged actions  

As the documentation states:  
> “More than 99.9% of common identity-related attacks are stopped by using multifactor authentication.”

Security defaults are ideal for:
- Small organizations  
- Tenants without Conditional Access  
- Free-tier Entra ID tenants  

---

## 🎯 Conditional Access & MFA

For more advanced scenarios, Conditional Access (requires Entra ID P1/P2) allows MFA to be required based on:

- User risk  
- Sign-in risk  
- Device compliance  
- Location  
- Application sensitivity  
- Session context  

Examples:
- Require MFA only when off the corporate network  
- Require phishing-resistant MFA for admin roles  
- Block access entirely from high-risk locations  

---

## 🧪 Primary vs Secondary Authentication

| Method | Primary | Secondary |
|--------|---------|-----------|
| Windows Hello for Business | Yes | MFA |
| Platform Credential (macOS) | Yes | MFA |
| Passkey (FIDO2) | Yes | MFA |
| Passkey in Authenticator | Yes | MFA |
| Synced Passkey | Yes | MFA |
| Certificate-Based Auth | Yes | MFA |
| Microsoft Authenticator (passwordless) | Yes | No |
| Microsoft Authenticator (push) | Yes | MFA/SSPR |
| Authenticator Lite | No | MFA |
| Hardware OATH | No | MFA/SSPR |
| Software OATH | No | MFA/SSPR |
| External MFA Providers | No | MFA |
| Temporary Access Pass | Yes | MFA |
| SMS Sign-In | Yes | MFA/SSPR |
| Voice Call | No | MFA/SSPR |
| QR Code | Yes | No |
| Email OTP | No | SSPR |
| Password | Yes | No |

---

## 🛠 Common IT Tickets You’ll See in This Area

| Ticket | Description | Typical Fix |
|--------|-------------|-------------|
| “I lost my phone and can’t sign in” | Lost MFA method | Issue TAP |
| “SMS codes not arriving” | Carrier issues | Switch to Authenticator |
| “MFA keeps failing” | Wrong method or CA policy | Check sign-in logs |
| “User stuck in MFA loop” | Conditional Access misconfiguration | Review CA policies |
| “Guest user can’t complete MFA” | Email OTP or external MFA issue | Enable guest OTP or adjust CA |

---

## 🧩 Troubleshooting Patterns

- Check **sign-in logs** for MFA requirement failures  
- Validate user’s **registered authentication methods**  
- Review **Conditional Access** policies  
- Ensure **Authenticator app notifications** are enabled  
- For passwordless, confirm device supports required hardware  
- For SMS/voice, verify phone number formatting  

---

## 📌 Key Takeaways
- MFA is essential — it blocks 99.9% of identity attacks  
- Microsoft Authenticator and passkeys provide the best balance of security and usability  
- Security defaults enforce MFA automatically  
- Conditional Access provides granular MFA control  
- Temporary Access Pass is critical for onboarding and recovery  
- SMS/voice should be phased out in favour of phishing-resistant methods  

