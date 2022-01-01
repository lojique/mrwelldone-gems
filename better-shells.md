# Python
```
python -c 'import pty; pty.spawn("/bin/bash")' 

python3 -c 'import pty; pty.spawn("/bin/bash")' 
```
```bash

www-data@remotehost$ ^Z

Mrwelldone@htb[/htb]$ stty raw -echo
Mrwelldone@htb[/htb]$ fg

[Enter]
[Enter]
www-data@remotehost$
```


## Others
```bash

/usr/bin/script -qc /bin/bash /dev/null

```

```bash

/bin/sh -i 
python3 -c "__import__('subprocess').call(['/bin/bash'])" 
perl -e 'exec "/bin/sh";' 
perl: exec "/bin/sh"; 
perl -e 'print `/bin/bash`' 
ruby: exec "/bin/sh" 
lua: os.execute('/bin/sh') 
```
