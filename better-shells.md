# Python
```
python -c 'import pty; pty.spawn("/bin/bash")' 

python3 -c 'import pty; pty.spawn("/bin/bash")' 
```
```bash

www-data@remotehost$ ^Z

Mrwelldone@htb[/htb]$ stty raw -echo;fg

[Enter]
[Enter]
www-data@remotehost$


# In zsh, you need to put the stty raw -echo;fg on one line, or it will break.


```
* We may notice that our shell does not cover the entire terminal. To fix this, we need to figure out a few variables. We can open another terminal window on our system, maximize the windows or use any size we want, and then input the following commands to get our variables:

![image](https://user-images.githubusercontent.com/96658935/147855760-b2eb3af4-c441-4990-ba0a-ba0fc8741e66.png)

```bash

www-data@remotehost$ export TERM=xterm-256color

www-data@remotehost$ stty rows 67 columns 318

```
Once we do that, we should have a netcat shell that uses the terminal's full features, just like an SSH connection.

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
