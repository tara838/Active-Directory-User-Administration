If your organization has thousands or ten thousands or even more accounts it would be a tedious and wasteful to navigate through all the OUs manually. ADUC has a Search filter to help you with it
![[search-filter-to-find.png]]

From here you can right-click on a user and perform many different actions with it
![[reset-password-window-dialog.png]]

But let's assume that this user `Victor Klein` works remotely and connects to our systems via VPN. To establish a VPN tunnel  user needs to have a needs valid domain credentials (not expired). However, because the password status is flagged as "expired" (requiring a reset), the VPN gateway will reject the login attempt. But without active VPN connection can't communicate with Domain Controller. 
Thus  the user becomes permanently locked out, as they cannot connect to change the password, and cannot change the password without connecting.

In this situation we uncheck the *The user must change the password at next login*, typing a secure random password and transmit the password to user via established secure channel. 

In this window you can also unlock the user account in case of actions that triggers account lock (e.g. violate failed login attempts, etc.). 
![[reset-password-uncheck-change.png]]

**Important: Don't blindly reset a password. Verify the identity of the person that asked you to reset password. Ask follow-up question to prove their identity like 'tell me your username/telephone/email' etc.**

**And double-check that you resetting password for the correct use. Because I think you don't want to create two issues out of the blue**
