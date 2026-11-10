Think of Organizational Unit (OU) as an folder/directory that contains Active Directory objects like Users, Computers, Server etc. You can link Group Policy Objects to them to restrict/allow some security settings. And all objects within OU inherit these GPOs.

The process of creating new OU is straightforward.
![[create-OU.png]]

We can create OU that is protected from deletion 
![[create-ou-window.png]]

If we try to delete this OU we will get the error message that says `You don't have permissions to perform this action`.
![[errot-delete-protected-ou.png]]

To delete this protected OU it is needed to enable `Advances Features` under View tab.
Then navigate to OUs properties and untick the checkbox `Protect object from accidental deletion`
![[untick-protected-ou.png]]

Having done that, we will be able to delete this OU.