# 🔐 Microsoft Entra – Self-Service Password Reset (SSPR) Lab (Quick Steps)

## 🧪 Exercise: Perform Basic SSPR Tasks

⏱ Duration: ~15 minutes  

---

## 🧩 Task 1 – Configure SSPR for a Group

Step 1 > Go to https://entra.microsoft.com  
Step 2 > Log in  
Step 3 > Navigate: Protection > Password reset  
Step 4 > Locate "Self service password reset enabled"  
Step 5 > Select "Selected"  
Step 6 > Click "No groups selected"  
Step 7 > Choose Project23 group  
Step 8 > Click Select  
Step 9 > Click Save  

---

## 🔐 Subtask 1 – Configure Authentication Methods

Step 1 > Go to Password reset > Authentication methods  
Step 2 > Set Number of methods required = 1  
Step 3 > Enable:
- Email  
- Mobile phone  
- Mobile app code  
Step 4 > Click Save  

---

## 📝 Subtask 2 – Configure Registration

Step 1 > Go to Password reset > Registration  
Step 2 > Set "Require users to register when signing in" = Yes  
Step 3 > Set reconfirmation interval = 90 days  
Step 4 > Click Save  

---

## 🔔 Subtask 3 – Configure Notifications

Step 1 > Go to Password reset > Notifications  
Step 2 > Ensure "Notify users on password reset" = Yes  
Step 3 > Set "Notify all admins when admins reset password" = Yes  
Step 4 > Click Save  

---


## ✅ Summary Flow

Enable SSPR > Assign Group > Configure Auth Methods > Enforce Registration > Enable Notifications



# 🔐 Microsoft Entra – Self-Service Password Reset (SSPR) (Summary)

## 📌 Overview
Self-Service Password Reset (SSPR) allows users to:
- Reset or change passwords without IT support  
- Recover access if they forget their password or get locked out  

✅ Benefits:
- Reduces helpdesk workload  
- Improves user productivity  
- Enhances security  

---

## 🧠 How SSPR Works

Step 1 > User selects Sign in  
Step 2 > Enters email  
Step 3 > Clicks Forgot password  
Step 4 > Chooses verification method (Email OTP / SMS)  
Step 5 > Receives one-time passcode  
Step 6 > Enters passcode  
Step 7 > Creates new password  

✅ Result:
User regains access without admin help  

---

## ⚙️ Prerequisites

- External tenant created  
- Role: Security Administrator  
- User flow configured  

---

## 🧩 Enable SSPR (User Flow)

Step 1 > Go to https://entra.microsoft.com  
Step 2 > Switch to external tenant  
Step 3 > Navigate: External Identities > User flows  
Step 4 > Select user flow  
Step 5 > Ensure Email with password is enabled  
Step 6 > Save  

---

## 🔐 Enable Authentication Method (Email OTP)

Step 1 > Go to Authentication methods  
Step 2 > Select Email OTP  
Step 3 > Enable method  
Step 4 > Choose:
- All users OR  
- Selected groups  
Step 5 > Click Save  

---

## 🔗 Enable Password Reset Link (Optional)

Step 1 > Go to Company Branding  
Step 2 > Edit Default sign-in  
Step 3 > Show "Self-service password reset"  
Step 4 > Save  

✅ Result:
Forgot password link visible on sign-in page  

---

## ✅ Test SSPR

Step 1 > Open app  
Step 2 > Click Sign in  
Step 3 > Enter email  
Step 4 > Click Forgot password  
Step 5 > Enter OTP (email or SMS)  
Step 6 > Set new password  

✅ Result:
Password successfully reset  

---

## ✅ Summary Flow

Enable User Flow > Configure Auth Method > Show Reset Link > Test SSPR  

---

## 🧠 Key Takeaways

- Users can reset passwords without IT  
- Uses Email OTP or SMS verification  
- Works with external (customer) identities  
- Improves security + reduces support load  

---

## 🔐 Security Insight

👉 SSPR + MFA = Strong account recovery protection  

(Prevents unauthorized password resets)
