```bash
Mrwelldone@htb[/htb]$ sudo -l

    (user : user) NOPASSWD: /bin/echo
    
```

The NOPASSWD entry shows that the /bin/echo command can be executed without a password. 
This would be useful if we gained access to the server through a vulnerability and did not have the user's password.
As it says user, we can run sudo as that user and not as root. To do so, we can specify the user with -u user:

```bash
Mrwelldone@htb[/htb]$ sudo -u user /bin/echo Hello World!

    Hello World!
```
