# Detection

```bash

ls -la /etc/passwd
ls -la /etc/shadow
```

![image](https://user-images.githubusercontent.com/96658935/147590168-9303fc1e-032f-47d3-8b20-cfb2ea716457.png)

A regular user isn't suppose to have read access to the /etc/shadow file.


# SSH Sensitive Files

```bash
find / -name authorized_keys 2> /dev/null
```

This one will show you authorized keys if you have access.

```bash

find / -name id_rsa 2> /dev/null

```

This one will show you id_rsa if you have access.



![image](https://user-images.githubusercontent.com/96658935/147592698-b3f0abcb-d38a-4d30-9385-2fdc3a961470.png)


* save the private key to your machine (assuming this is the key to teh root accoount)
* once saved give the file chmod 600 permissions
* then execute this command

```bash
ssh -i <file name> <user>@<IP>
```
