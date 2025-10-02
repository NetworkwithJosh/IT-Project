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
![Screenshot](images/duo1-1.jpg)
---   
## Duo Mobile Dashboard

### Users
- Add, manage, and remove user accounts.
![Screenshot](images/mfa3.png)
### Devices
- Shows al registered phones, hardware tokens, etc.
### Policies
- Set up rules for MFA (such as require MFA, allowed devices, geolocation rules).
![Screenshot](images/mfa4.png)
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
![Screenshot](images/mfa5.png)
## Send an Enrollment Email

- The user receives an email for Duo Security enrollment.
- The user enrolls with Duo Mobile app by adding their phone number and fingerprint to enroll successfully.
![Screenshot](images/mfa6.png)
![Screenshot](images/mfa7.png)

##  Notes
- **NB:** MFA should always be active.
- Never use **Bypass** (which allows skipping two-factor authentication).
- Always seek management approval before granting a bypass.
---
## Groups
- Groups make it easy to manage users in a more simplified way.
- Manage applications at scale and quickly enable or disable users in bulk.
- Navigate to:
    - `Users` → `Groups` → `Add Groups`
  - Name the group and add a description, then click **Add Group**.
  - Add users to the group:
    - Select users to add
    - Click **Add users to group**
![Screenshot](images/mfa8.png)
---
## Adding Administrator
- Assign an administrator with fewer powers to complete simple tasks.
- Add the name and email address.
- Since I’m aiming for Help Desk, I assign the **Help Desk** role.
![Screenshot](images/mfa9.png)
---
## Applications
- Applications: Integrate Duo into one or more of your services.
- You can protect as many applications with Duo as you need.
![Screenshot](images/mfa10.png)
# Enabling MFA for Windows Server (via Duo)

## Adding Duo to Applications

Once you navigate to:
- `Applications` → `Protect Applications`
- Select the application and click on **Add**

> So when a user tries to access Microsoft RDP, it must prompt for 2-factor authentication.
![Screenshot](images/mfa12-1.png)
---

## Enabling MFA on Windows Server 2022

Adding an extra layer of defense for Windows Server is really important to avoid cyber attacks and helps to harden security. Only approved individuals are allowed to access the Windows Server.

### Steps:

- Log into the **Duo Mobile App** (with credentials and push log-in with your mobile phone)
- Navigate to `Dashboard` → `Select Applications`
- Select application: **Microsoft RDP**
- Find application and search for **Microsoft RDP** on server
- Join through the policies and click **Save**
- Click on **RDP Documentation** to integrate Duo with your Microsoft RDP deployment
![Screenshot](images/mfa12.png)
![Screenshot](images/mfa12-1.png)

---
## Final Configuration
- Scroll down to:
  - **Duo authentication for Windows Logon Installer Package (No 8)**
![Screenshot](images/mfa13.png)
### Integration:
- Copy the **API hostname**
- Navigate back to the details and paste the API hostname
- Add the **Integration Key** and **Security Key** from the deployment log
![Screenshot](images/mfa14.png) ****
## Testing Duo After Final Install
- Click on video and finish the installation.
- Once it's done, test if it works.
- Go to `Devices` → `Phones or Endpoint` → Devices enrolled to Duo.
- You will see all the devices managed by your organization.
- For my test, I only have one device here (sent from Luke for use).
- You can send Duo push to verify the user’s identity.
![Screenshot](images/mfa15.png)
---
## Troubleshooting Duo Help Desk Issues

### Scenario:
User gets a new phone. When trying to log in to their email or VPN, the Duo prompt fails or doesn’t show.
### Steps:
- Verify user's identity.
- Check if they still have access to Duo on old phone or not.
- Navigate to Duo Admin Panel → `Users` → Scroll down to the user.
- Remove/delete old device → Add a new device.
- Choose Mobile → Enter their number → They install the Duo app.
- Scan the QR Code.
![Screenshot](images/mfa16.jpeg)
![Screenshot](images/mfa17.png)
![Screenshot](images/mfa18.png)

---

**Note:** Guiding the user through the process is very vital for the role of an IT Helpdesk agent.
