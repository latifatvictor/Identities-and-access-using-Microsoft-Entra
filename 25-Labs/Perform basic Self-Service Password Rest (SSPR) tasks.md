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
