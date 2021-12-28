```bash

sudo -l

```
The target system may be configured to allow users to run some (or all) commands with root privileges. 
The sudo -l command can be used to list all commands your user can run using sudo

```bash

ls -la
```
This commands shows hidden files. You may find a file with credentials.



```bash
/etc/passwd
```
This command will show you the users on a system.


```bash
find / -perm -o x -type d 2>/dev/null
```
Find world-executable folders

```bash
find / -perm -u=s -type f 2>/dev/null
```
Find files with the SUID bit, which allows us to run the file with a higher privilege level than the current user. 
