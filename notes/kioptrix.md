# Kioptrix
- Username: john
- Password: TwoCows2
- ping 8.8.8.8 -- to find ip address
- Run this from your attacker machine to find ip. Look for VMware-- ```arp-scan -l```

## Nmap
- -A will give you the sV,sC,o triggers
- Use -p- for exam

## Enumerating http and https
Information disclosure  
Default webpage - apache - PHP  
<img width="1463" height="575" alt="image" src="https://github.com/user-attachments/assets/8d95a935-e3f2-47f8-ac24-a3396fda2a62" />  
<img width="801" height="181" alt="image" src="https://github.com/user-attachments/assets/8840657e-1678-4178-a613-63489e569e17" />  

### Nikto
Can be used for vulnerability scanning web servers
- ```nikto -h http://(ip address)```
- Save Scan and keep in your notes
- Finding<img width="1482" height="665" alt="image" src="https://github.com/user-attachments/assets/41d8991b-075f-463d-9722-39eee39488be" />

## Enumerating SMB
### Metasploit
- auxiliary/scanner/smb/smb_version
- 
### SMBClient
- ```smbclient -L \\\\(ip address)\\```
- Then you can command similar to linux

## Enumerating SSH
- ```ssh (ip address) -oKexAlgorithms=+ diffie-hellman-group1-sha1 -c (copy the aes part)```
