# Powershell Automation (Active Directory)

## Overview
PowerShell Active Directory refers to the use of the Active Directory module for Windows PowerShell to manage and automate tasks in Microsoft Active Directory.  

It uses PowerShell commands (cmdlets) to perform operations such as:
- Creating, modifying, and deleting users and computers  
- Managing groups and organizational units  
- Resetting passwords and unlocking accounts  
- Querying Active Directory for information (e.g., last logon times, group membership)
- Automating bulk changes across multiple objects 
---
## Getting Started
To work with PowerShell in Active Directory, you need to import the module to get the commands for Active Directory automation.  
##  Steps:
1. Navigate to the Start Menu → search for **PowerShell**  
2. Right-click and **Run as Administrator**  
3. In PowerShell, run:
   Import-Module Active Directory
![Screenshot](images/Automation1.jpg)
4. Get-Command  (shows Different command to use) to run scripts.
![Screenshot](images/Automation2.jpg)
## Creating a New Organizational Unit (OU) with PowerShell  

You can create a new OU in Active Directory using this cmdlet:
  
`New-ADOrganizationalUnit -Name "CentralUnit" -Path "DC=joshua,DC=local"`

- `-Name` specifies the OU name

- `-Path` specifies the domain structure where it will be create
![Screenshot](images/Automation3.jpg)
![Screenshot](images/Automation4.jpg)
# Creating More OUs with PowerShell

* Creating Sub OUs inside Central Unit with PowerShell
* Created another sub OUs under Student for Gryffindor to add a user inside.
![Screenshot](images/Automation5.jpg)
![Screenshot](images/Automation6.jpg)

# Using PowerShell, I created a New User account in Active Directory

  Using the Cmdlet:
  ![Screenshot](images/Automation7.jpg)

```
```powershell
New-ADUser -Name "Harry Potter" -SamAccountName "hpotter" -UserPrincipalName "hpotter@Njikason.com" -Path "OU=Gryffindor, OU=Student, OU=CentralUnit, DC=Joshua, DC=local" -AccountPassword (ConvertTo-SecureString "Capitolp123" -AsPlainText -Force) -Enabled $true -ChangePasswordAtLogon $true
```
- Created User account (Harry Potter) using the above Script.
![Screenshot](images/Automation8.jpg)
- Created another User account (Hermione Granger) using the same script.
![Screenshot](images/Automation9.jpg)
![Screenshot](images/Automation10.jpg)


---
# Get-ADUser

- `Get-ADUser` is used to retrieve information about a User account in Active Directory (AD) and also properties like email, groups, account information.
![Screenshot](images/Automation11.jpg)


---
# Adding Email Address to a User

- Adding email address to the user Harry Potter on PowerShell:
    
`Set-ADUser -Identity "hpotter" -Email "harry.potter@njikason.com" -OfficePhone "800-555-7777"`
![Screenshot](images/Automation13.jpg)
![Screenshot](images/Automation14.jpg)

---
- ## Disable account with PowerShell:
    
`Set-ADUser -Identity "hgranger" -Enabled $false`

- ## To enable the account again:
    
`Set-ADUser -Identity "hgranger" -Enabled $true`
![Screenshot](images/Automation15.jpg)
![Screenshot](images/Automation16.jpg)
# Resetting Password with PowerShell on Active Directory

* Navigate to PowerShell and type:

```powershell
Set-ADAccountPassword -Identity "hpotter" -Reset -NewPassword (ConvertTo-SecureString "Capitolp123" -AsPlainText -Force)

```
![Screenshot](images/Automation17.jpg)
- Then prompt for the user to change their password at the next logon:
    
`Set-ADUser -Identity "hpotter" -ChangePasswordAtLogon $true`
![Screenshot](images/Automation18.jpg)
The password has been changed.
![Screenshot](images/Automation19.jpg)

---
# Unlocking a User Account in Active Directory

- Navigate to PowerShell → open as Administrator → type:
    
`Unlock-ADAccount -Identity "hpotter" Unlock-ADAccount -Identity "hgranger"`
![Screenshot](images/Automation20.jpg)

---
# Creating a Group (Security Group) Using PowerShell

- In PowerShell type:
`Add-ADGroupMember -Identity "Quidditch Players" -Members "hgranger"`
![Screenshot](images/Automation21.jpg)
![Screenshot](images/Automation22.jpg)

---
# Creating Another User with PowerShell

- Created another user account (**Ron Weasley**)using PowerShell and added to Gryffindor group OU with created password
![Screenshot](images/Automation23.jpg)
![Screenshot](images/Automation24.jpg)

---
# Automation in powershell:

### Automation in powershell is the process of writing Scripts to perform repetitive IT tasks without manual efforts. Instead of clicking through GUI (Active Directory users & Computers) you use powershell Cmdlets to Script the process once and re-use it many times.
