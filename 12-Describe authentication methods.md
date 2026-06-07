## Authentication Methods in Microsoft Entra ID

### 📘 Summary
Authentication verifies a user’s identity before granting access to apps, services, devices, or networks.  
Microsoft Entra ID supports a wide range of authentication methods that balance **security**, **usability**, and **deployment needs**.

The modern goal is to move away from passwords and toward **phishing-resistant, passwordless authentication**.

---

## 🔐 Passwords (Legacy Method)
Passwords are still widely used but are:
- Easy to compromise  
- Hard to manage securely  
- A productivity drain when forgotten  

**Best practice:**  
Use passwords **only** as a fallback. Supplement or replace them with stronger methods.

---

## 📱 Phone-Based Authentication

### SMS Sign-In
- User enters phone number → receives a verification code  
- Can be used as **primary authentication**  
- Also used for **SSPR** and **MFA**

### Voice Call
- Automated call prompts user to press **#**  
- Only supported as **secondary authentication**  
- Not recommended for modern security

**Microsoft recommendation:**  
Move away from SMS/voice toward **Authenticator** or **passkeys**.

---

## 🔢 OATH (Time-Based One-Time Passwords)

### Software OATH Tokens
- Apps like Microsoft Authenticator  
- Generate TOTP codes every 30–60 seconds  

### Hardware OATH Tokens
- Physical key fobs displaying rotating codes  

**Use case:**  
Secondary authentication for **MFA** or **SSPR**.

---

## 🧩 Other Authentication Methods

### Temporary Access Pass (TAP)
- Time-limited passcode issued by admin  
- Used for onboarding or recovery  
- Allows registration of passwordless methods

### QR Code Authentication
- Designed for frontline/shared devices  
- User scans QR code + enters PIN  
- No need to type usernames/passwords

### Email OTP
- One-time code sent to email  
- Used for **SSPR** or **guest sign-in**

### Platform Credential for macOS
- Passwordless, phishing-resistant  
- Uses Secure Enclave + Touch ID

### Authenticator Lite
- MFA inside Outlook Mobile  
- No need for full Authenticator app

### External Authentication Methods
- Integrate Duo, RSA SecurID, etc.  
- Used to satisfy MFA requirements

---

## 🔑 Passwordless Authentication (Recommended)

Passwordless combines:
- **Something you have** (device, key)  
- **Something you are** (biometrics)  
- **Something you know** (PIN)  

### Windows Hello for Business
- Strong 2FA tied to device  
- Uses biometrics or PIN  
- Resistant to credential theft

### Passkeys (FIDO2)
Phishing-resistant public key cryptography.

Two types:
- **Device-bound passkeys** (FIDO2 keys, Authenticator)  
- **Synced passkeys** (iCloud Keychain, Google Password Manager)

### Microsoft Authenticator
Supports:
- Passkeys  
- Passwordless sign-in  
- Push notifications with number matching  
- OATH codes  

### Certificate-Based Authentication (CBA)
- Uses X.509 certificates  
- Cloud-native alternative to AD FS  
- Supports primary and MFA scenarios

---

## 🛡️ Phishing-Resistant Authentication (Most Secure)
Microsoft recommends these methods due to AI-driven phishing threats:

- Windows Hello for Business  
- Platform Credential for macOS  
- Passkeys (FIDO2)  
- Passkeys in Microsoft Authenticator  
- Certificate-Based Authentication (CBA)

These methods:
- Bind credentials to the legitimate domain  
- Cannot be replayed  
- Cannot be phished  

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

## 🏢 Real-World Scenarios & Practical Notes

### Scenario 1: User Loses Phone → Cannot Access MFA
**Fix:**  
Issue a **Temporary Access Pass (TAP)** so the user can re-register methods.

### Scenario 2: High-Risk Department Needs Phishing-Resistant MFA
**Solution:**  
Deploy **FIDO2 passkeys** or **Windows Hello for Business**.

### Scenario 3: Frontline Workers on Shared Devices
**Solution:**  
Use **QR code authentication** + PIN.

### Scenario 4: Legacy MFA Provider Already in Use
**Solution:**  
Enable **external authentication methods** (e.g., Duo).

---

## 🛠 Common IT Tickets You’ll See in This Area

| Ticket | Description | Typical Fix |
|--------|-------------|-------------|
| “I changed phones and can’t sign in” | Lost authenticator | Issue TAP |
| “SMS code not arriving” | Carrier issues | Switch to Authenticator |
| “Need passwordless setup” | Security upgrade | Deploy passkeys or WHfB |
| “MFA keeps failing” | Wrong method | Check registered methods |
| “Guest user can’t sign in” | Email OTP issues | Enable guest OTP |

---

## 🧩 Troubleshooting Patterns

- Check **registered authentication methods** first  
- Use **Sign-in logs** to identify failures  
- For MFA issues, verify **Conditional Access**  
- For passwordless, ensure device supports required hardware  
- For passkeys, check browser and OS compatibility  

---

## 📌 Key Takeaways
- Passwordless and phishing-resistant methods are the future  
- Microsoft Authenticator is the most versatile option  
- Passkeys (FIDO2) provide the strongest protection  
- TAP is essential for recovery and onboarding  
- SMS/voice should be phased out  
- Authentication method choice impacts both security and user experience  

