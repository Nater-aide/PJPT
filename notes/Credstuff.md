# Credential stuffing and Password spraying
## Burp
## Credential stuffing
1. Navigate to webpage login
2. launch Burp
3. enter fake information
4. Send to Intruder
5. Click positions and clear
6. Highlight username and click add
7. highlight password and click add
8. Attack types
   - Sniper -- uses one paramter
   - Pitchfork -- uses two parameters
9. For pitchfork, go payloads
10. Paste your list of users
11. Paste your lists of passwords
12. Press attack
13. Look for status code changes (you want a 301 or change in length)
14. You can check into response and look for a failed login response
15. Copy the response, go to options and use the Grep feature
16. Clear grep info
17. paste the error

## Password spraying
1. gather list of all users we can think of
2. Use the same technique as above but use one parameter
