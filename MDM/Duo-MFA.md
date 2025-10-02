# Duo Mobile / MFA

## What is Duo Mobile?
Is a multi-factor authentication (MFA) app developed by Cisco Duo Security. It helps protect your accounts by requiring a second layer of verification (in addition to your password) whenever you log in.

## How it Works?
- You install Duo Mobile on your smartphone.
- When you try to log in to a system that uses Duo, you enter your username and password.
- Instead of logging in immediately, the system sends a push notification or code request to your phone.
- You confirm the login by tapping “Approve” in the Duo Mobile app, or by entering a passcode it generates.

## Key Features?
- Push Notifications: Simplifies login by just tapping “Approve.”
- Passcodes: Works even without internet or cell service by generating temporary codes.
- Biometric Support: Can use fingerprint or face recognition on your phone for extra security.
- Wide Use: Commonly used by universities, corporations, and healthcare providers to secure VPNs, email, cloud apps, and remote access.

## Examples
- If you’re logging into your university email from a new laptop, you’ll type your password, then get a Duo push on your phone. You tap “Approve,” and access is granted.

**Note:** Guiding the user through the process is very vital for the role of an IT Helpdesk agent working in IT.
![Screenshot](images/mfa1.png)
## What is Multi-factor Authentication?
(MFA) is a security process that requires users to provide two or more types of verification before gaining access to an account, system, or application. The idea is to add extra layers of protection beyond just a username and password.

### MFA typically combines at least two of these categories:
- Something you know – a password, PIN, or security question.
- Something you have – a smartphone app (like Duo Mobile, Google Authenticator), a hardware token, or a smart card.
- Something you are – biometric identifiers such as a fingerprint, facial recognition, or voice pattern.

### Example 
- For example, when you log in to your email, you might first enter your password (something you know) and then confirm a push notification on your phone (something you have).

---
##  Setting up Duo Mobile

Setting up Duo Mobile is **simple and straightforward**:

1. Go to the website: [signup.duo.com](https://signup.duo.com)
2. Fill out the **Sign-up Form**:
![Screenshot](images/mfa2.png)
   - Full name  
   - Work email  
   - Phone number  
   - Country
3. Click on **Sign Up** and **Verify your email address**
4. You will be prompted to verify your phone number
5. Install Duo Mobile on a smartphone and link it as your admin device.
![Screenshot](images/mfa3.png)
---   
## Duo Mobile Dashboard

### Users
- Add, manage, and remove user accounts.
![Screenshot](images/mfa4.png)
### Devices
- Shows al registered phones, hardware tokens, etc.
### Policies
- Set up rules for MFA (such as require MFA, allowed devices, geolocation rules).
![Screenshot](images/mfa5.png)
### Applications
- Where you integrate Duo with services like Microsoft 365, VPNs, RDP, etc.
### Reports, Monitoring & Billings
- These are essential parts of Duo for reports and monitoring.
- Check billing and usage data.
---
## Creating a User Account on Duo

1. Navigate to:
   - Users → Add Users (also supports Bulk End Users or Import Users)
2. Enter the username and email address of the user.
3. Click **Add User**.
![Screenshot](images/mfa.png)
## Send an Enrollment Email
