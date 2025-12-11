# Setting up Domain Controller
For PJPT set
1. Install in VirtualBox
2. Rename Server to HYDRA-DC
3. Install Guest additions
4. Reboot

## Make this server a domain controller
1. Click Manage
2. Add Roles and Features
3. Role based or feature based installation
4. Next
5. Add the **Active directory domain services**
6. Click **restart the destination server automatically if required**
7. Click Install
8. **Promote this server to a domain controller**
9. **Add new forest**
10. Name it MARVEL.local
11. Enter a password

Domain Controller
 - Name: HYDRA-DC
 - Username: vboxuser
 - Password: P@$$w0rd!

Domain
- MARVEL.local
