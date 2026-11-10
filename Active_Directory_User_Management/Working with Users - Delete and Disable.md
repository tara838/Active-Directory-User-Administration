
To disable account: find a user via search filter, right click -> disable account
![[disable-account.png]]


To keep track of disabled accounts we will add them  to previously created `Disabled Users` OU. It's convenient because we can apply automation via PowerShell to parse through OU and disable all accounts that are within it or tell us who are in there. It's possible to create Group Policy Objects and apply policies to the `Disaled OUs` something like, do not allow login to the computers if the account is in this OU etc.

![[klein-in-disabled-users-OU.png]]


To delete account: right click -> Delete 
![[delete-user.png]]


**Important: Double-check your action because you can't easily undo what you deleted in Active Directory**
