# Python
```
python -c 'import pty; pty.spawn("/bin/bash")' 

python3 -c 'import pty; pty.spawn("/bin/bash")' 
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
