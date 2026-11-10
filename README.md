# Active Directory: Day-to-Day User Administration

Hands-on practice of the routine tasks an IT support or junior system administrator performs in Active Directory every day: organizing accounts into Organizational Units (OUs) and managing the full life cycle of a user account (create, reset password, unlock, disable, delete).

All tasks were done in the Active Directory Users and Computers (ADUC) console on a Windows Server domain controller.

> Related project: [Virtual Home Lab: Windows and Linux Enterprise Environment](https://github.com/tara838/virtual-home-lab), where I built the domain, DNS, DHCP, Group Policy and a Linux file server.

## Tasks covered

| Task                    | Where in ADUC                                    | Result                                         |
| ----------------------- | ------------------------------------------------ | ---------------------------------------------- |
| Create and manage OUs   | Right-click the domain, New, Organizational Unit | Accounts organized by department               |
| Create a user account   | Right-click the OU, New, User                    | New employee can log in                        |
| Reset a password        | Right-click the user, Reset Password             | User gets access back, must set a new password |
| Unlock an account       | Account tab (or the reset dialog)                | Locked-out user can log in again               |
| Disable an account      | Right-click the user, Disable Account            | Access removed, account kept                   |
| Delete an account or OU | Right-click, Delete                              | Object removed after a safe process            |

## What I learned

- Accounts have a life cycle: create, change, disable, delete. Each step has a safe way to do it.
- Reset password, unlock account and disable account are different actions and are used in different situations.
- Make changes with an administrative account and confirm the result from the user's side.
- Protecting OUs from accidental deletion prevents costly mistakes.

## Skills demonstrated

Active Directory user and OU management, ADUC, password and account lockout handling, access removal for leavers, basic support workflow.

## Same tasks in PowerShell

```powershell
New-ADOrganizationalUnit -Name "Sales" -Path "DC=example,DC=internal"
New-ADUser -Name "Jane Doe" -SamAccountName "jane.doe" -Path "OU=Sales,DC=example,DC=internal" -AccountPassword (Read-Host -AsSecureString "Temporary password") -ChangePasswordAtLogon $true -Enabled $true
Set-ADAccountPassword -Identity jane.doe -Reset
Unlock-ADAccount -Identity jane.doe
Disable-ADAccount -Identity jane.doe
Remove-ADUser -Identity jane.doe
```
