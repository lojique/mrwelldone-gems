Much of Linux privilege controls rely on controlling the users and files interactions. 
This is done with permissions. 
By now, you know that files can have read, write, and execute permissions.
These are given to users within their privilege levels. 
This changes with SUID (Set-user Identification) and SGID (Set-group Identification).
These allow files to be executed with the permission level of the file owner or the group owner, respectively.

```bash
find / -type f -perm -04000 -ls 2>/dev/null
```

```bash

find / -perm -u=s -type f 2>/dev/null
```
will list files that have SUID or SGID bits set

![image](https://user-images.githubusercontent.com/96658935/147518758-e5d7d0d5-bae0-4b39-9298-8c305507c6a9.png)


![image](https://user-images.githubusercontent.com/96658935/147518812-f344d8b7-5aa0-4012-bb3d-ed480a1ac617.png)

A good practice would be to compare executables on this list with GTFOBins (https://gtfobins.github.io).
Clicking on the SUID button will filter binaries known to be exploitable when the SUID bit is set 
(you can also use this link for a pre-filtered list https://gtfobins.github.io/#+suid).
