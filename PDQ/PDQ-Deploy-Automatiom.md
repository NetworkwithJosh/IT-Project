# PBQ Deploy

## What is PDQ Deploy?

PDQ Deploy is a remote software deployment tool for Windows environments. It allows you to push software, scripts, patches, and updates to multiple machines simultaneously or on a schedule.

You can see it as your "remote software installer."
Instead of going from PC to PC, you send out one command and PDQ takes care of the rest.
As a  Helpdesk I might approval from management to install software application to client machine silently without interrupting their work.

![Screenshot](images/PDQ1.jpg)

---
## What Does It Do?

- Silently installs applications (e.g. Chrome, Zoom, Adobe Reader)
- Updates software and deploys custom scripts
- Schedules deployments (e.g install at night)
---
## Setting up PDQ Deploy on Server 2022 (My Lab Environment)

- My Windows Server 2022 has a static IP.
  In order to download PDQ, I had to change it to a dynamic IP address.
![Screenshot](images/PDQ2.jpg)
### Steps:
1. Navigate to **Control Panel** → **Network** → **Change Adapter Settings**
2. Go to PDQ official website
3.  Sign up for 14-day trial
4.  Fill in my details and verify my email account
5. Download PDQ Deploy and input the license key
![Screenshot](images/PDQ3.jpg)
![Screenshot](images/PDQ3-1jpg)
## PDQ Dashboard Overview

- The Dashboard shows:
 - All Deployments
 - All apps deployment to endpoints
 - All schedules
 - Retry queue
 - Package Library
![Screenshot](images/PDQ4.jpg)
### Package Library
- This is where all the apps are located
---
## Deploying Application on Server 2022

- Go to **Package Library**
- Select the app (in my lab: Zoom
- Right-click the app → Select **Download Selected**
- As app downloads, it gets added to local library
![Screenshot](images/PDQ5.jpg)
1. Go to **Package**
2. Select the app package
3. Right-click → Select **Deploy Once**
![Screenshot](images/PDQ6.jpg)
4. On the top right, click on **Targets**
5. Select **Active Directory** → **Computers**
  - As you can see, I have two computers.
  - Since I'm deploying Zoom to Windows Server 2022:
    - Select it
  ![Screenshot](images/PDQ7.jpg)
     - Click on the single arrow →
  ![Screenshot](images/PDQ8.jpg)
    - Click on **OK**
    - Then **Deploy Now**
  ![Screenshot](images/PDQ9.jpg)
  ![Screenshot](iages/PDQ10.jpg)

  > Now it's completed and fully deployed to my Server 2022.
  ![Screenshot](images/PDQ11.jpg)
  ## Deploying 7-Zip PDQ Deploy on Windows Server 2022
