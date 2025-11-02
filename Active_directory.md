# Active directory

In this course i will review what i did during my studies about AD DS
I will take the role of a IT Network Administrator in a company

## OU and users

First task was to create a new OU called Students, i went directly to the AD DS config menu and added it into the AD DS
I also searched how to do it with the Powershell just to refresh memory

```
PS C:\> New-ADOrganizationalUnit -Name "UserAccounts" -Path "OU=THM,DC=thm,DC=local"
```
I created a new OU in athe THM OU to separate one from the other

I gave powers to a user to reset passwords and manage accounts via the AD management, then i connected to the user via RDP and reseted a password

Using 
```
Set-ADAccountPassword -Identity "sophie" #user1st -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose
Set-ADUser -ChangePasswordAtLogon $true -Identity sophie -Verbose #To reset the password at login
```

To change the password and the ask for a change when the person login

## Organizing computers

I created with the same script as before a new OU called Servers and Workstations to better organize and manage policies for each

GPO are a very important parto of network administration, they can give many computer standart configurations and rules
We access there by wiritig Group Policy Management in the search bar
<img width="954" height="577" alt="image" src="https://github.com/user-attachments/assets/fd1c7735-d171-476d-83ec-0a1598bc2eaf" />

Use remmina to remote connect





