## PDQ Inventory

### What is PQD Inventory?
PDQ Inventory is a systems management tool for Windows that helps IT administrators automatically scan, collect, and organize information about computers and devices in their network.
It scans and gathers system information from all computers on the network (CPU, RAM, indtalled apps, OS Version, etc)
![Screenshot](images/Inventory1.jpg)

### Computer Scanning & Data Collection
PDQ Inventory scans each machine to gather details such as:
- Hardware (CPU, RAM, disk space, etc.)
- Installed software and versions
- Operating system and patch levels
- Services, running processes, users, and event logs

### Centralized DataBase
- All the collected information is stored in a searchable database.
- Admins can group computers dynamically (for example, “all machines missing a specific update” or “all computers running Windows 10”).

### Integration with PDQ Deploy
- PDQ Inventory works closely with PDQ Deploy.
 For example:
   - You can create a group in Inventory for “computers missing Adobe Reader” and then use PDQ Deploy to push the Adobe Reader update only to those machines.

### Installing PDQ Inventory
- Download PDQ Inventory and copy license key.
- Launch the application → Accept terms → Next → Install
- ![Screenshot](images/Inventory2.jpg)
- Enter license key and email account → Select **Local**
- Choose installation type  → Enter credential password  → Finish
![Screenshot] 
### Launch PDQ Inventory
  ![Screenshot](images/Inventory3.jpg)
  PDQ Inventory gives you a run-down of everything installed on a computer: apps, updates, etc.
  In my project, I have Windows 11 added to the PDQ Inventory.

 ### Adding Computers

 - At the top → **Add Computers** → **Active Directory**
 - It Shows you all the computers on your Active Directory
 ![Screenshot](images/Inventory4.jpg)
 - Add to the target → Click **OK**
 ![Screenshot](images/Inventory5.jpg)
---
### Running Reports

- If you right-click on a computer → **Run Report**
- It gives you an in-depth report on:
   - Applications
   - Operating System
   - Shared Folders
![Screenshot](images/Inventory6.jpg)
![Screenshot](images/Inventory7.jpg)
![Screenshot](images/Inventory8.jpg)
### Shared Folders, Operating System, Applications

- Shared folders on the computer and installed applications can be viewed.
- To do this: Right-click on the computer → **View Computer Info**
![Screenshot](images/Inventory9.jpg)
- This shows all the details of the computer for general info and Active Directory.
---
### File Sharing
- You can go to `\\shared path` to place a file for the user.
- On the Windows 11 PC, the file is already there if properly shared.
![Screenshot](images/Inventory10.jpg)
### Remote Access

- Remoting into the computer from PDQ Inventory:
  - Click on the computer → On top (Tools) → **Remote Desktop**
![Screenshot](images/Inventory11.jpg)
 - Click **Connect** → Enter admin password → Now you have access.
![Screenshot](images/Inventory12.jpg)
- You can remote into Windows 11 from Windows Server without TeamViewer or AnyDesk.
![Screenshot](images/Inventory13.jpg)
![Screenshot](images/Inventory14.jpg)


---
### Reboot or Shutdown via PDQ

- PDQ Inventory also allows for **Reboot** or **Shutdown** of the machine
  - Go to: **Tools** → Reboot / Shutdown → OK
![Screenshot](images/Inventory15.jpg)
    ipconfig on windows 11 from PDQ Inventory.
![Screenshot](images/Inventory16.jpg)


---
### Application Reports

- To generate a report on applications:
  - Right-click on the PC → Scroll to **Run Report** → **Applications**
  - Print preview on the top
  - This reports on all the applications on the Windows 11 machine.

